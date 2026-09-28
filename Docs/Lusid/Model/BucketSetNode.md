# Finbourne.Sdk.Lusid.Model.BucketSetNode

One node within a bucket set result: the fund aggregate or a single share class. Both carry NAV and buckets; the  capital ratio, the unit counts and the per-unit values belong to share class nodes and are omitted on the fund node.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NodeType** | **string** | Required | The kind of node: the fund aggregate or a single share class. Available values: Fund, Class. |
| **ShareClassShortCode** | **string** | Optional | The short code of the share class this node is for. Omitted on the fund node. |
| **Nav** | **decimal?** | Optional | The net asset value at this node, in the fund currency. |
| **CapitalRatio** | **decimal?** | Optional | The share class&#39;s capital ratio (its share of the fund NAV). Omitted on the fund node. |
| **Buckets** | [List&lt;BucketSetResultBucket&gt;](BucketSetResultBucket.md) | Required | The buckets on this node, each with its period movement and cumulative values. |
| **PerUnitValue** | **decimal?** | Optional | The share class&#39;s NAV per unit in issue, in the fund currency, rounded to the share class&#39;s PricePrecision (left unrounded where the share class declares none). Omitted on the fund node, for a share class that is not unitised, and for a unitised share class with no units in issue to divide by (SharesInIssue is then reported as zero). The dealing price - in the share class currency, with its instrument&#39;s rounding convention applied - is on the share class breakdown&#39;s unitisation data. |
| **SharesInIssue** | **decimal?** | Optional | The share class&#39;s units in issue at the end of the period. Omitted on the fund node and for a share class that is not unitised. |
| **PreviousPerUnitValue** | **decimal?** | Optional | The share class&#39;s NAV per unit at the previous valuation point, on the same basis as PerUnitValue. Omitted on the fund node, for a share class that is not unitised, and where the share class had no units in issue at the previous valuation point (including the fund&#39;s first valuation point). |
| **PreviousSharesInIssue** | **decimal?** | Optional | The share class&#39;s units in issue at the start of the period. Omitted on the fund node and for a share class that is not unitised; zero at the fund&#39;s first valuation point. |
| **Label** | **string** | Optional | A display label for the node: the fund&#39;s display name on the fund node, the share class&#39;s name on a share class node. |
| **PreviousNav** | **decimal?** | Optional | The net asset value this node carried at the previous valuation point, in the fund currency. Zero at the fund&#39;s first valuation point. |
| **NetDealingUnits** | **decimal?** | Optional | The net units dealt for the share class over the period, so that the shares in issue are the previous shares in issue plus this. Omitted on the fund node and where the bucket set is not unitised. |
| **ShareClassDetails** | [BucketSetShareClassDetails](BucketSetShareClassDetails.md) | Optional | *No description available.* |
| **NavShareClassCurrency** | **decimal?** | Optional | The node&#39;s net asset value restated in the share class&#39; own currency, at the rate this node publishes. Set only on share class nodes. |
| **ShareClassToFundFxRate** | **decimal?** | Optional | The fx rate from the share class currency to the fund currency at this valuation point. Nav and the bucket values are in the fund currency, so divide by this rate to restate them in the share class currency. Set only on share class nodes. |
| **PreviousNavShareClassCurrency** | **decimal?** | Optional | The net asset value in the share class&#39; currency at the previous valuation point, as that point published it, at the rate that point struck. Zero at the fund&#39;s first valuation point. Absent (rather than zero) if the previous valuation point predates this field. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketSetNode(
    nodeType: "...",  // required — The kind of node: the fund aggregate or a single share class. Available values: Fund, Class.
    shareClassShortCode: "...",  // optional — The short code of the share class this node is for. Omitted on the fund node.
    nav: 0.0d,  // optional — The net asset value at this node, in the fund currency.
    capitalRatio: 0.0d,  // optional — The share class&#39;s capital ratio (its share of the fund NAV). Omitted on the fund node.
    buckets: new List<BucketSetResultBucket>(),  // required — The buckets on this node, each with its period movement and cumulative values.
    perUnitValue: 0.0d,  // optional — The share class&#39;s NAV per unit in issue, in the fund currency, rounded to the share class&#39;s PricePrecision (left unrounded where the share class declares none). Omitted on the fund node, for a share class that is not unitised, and for a unitised share class with no units in issue to divide by (SharesInIssue is then reported as zero). The dealing price - in the share class currency, with its instrument&#39;s rounding convention applied - is on the share class breakdown&#39;s unitisation data.
    sharesInIssue: 0.0d,  // optional — The share class&#39;s units in issue at the end of the period. Omitted on the fund node and for a share class that is not unitised.
    previousPerUnitValue: 0.0d,  // optional — The share class&#39;s NAV per unit at the previous valuation point, on the same basis as PerUnitValue. Omitted on the fund node, for a share class that is not unitised, and where the share class had no units in issue at the previous valuation point (including the fund&#39;s first valuation point).
    previousSharesInIssue: 0.0d,  // optional — The share class&#39;s units in issue at the start of the period. Omitted on the fund node and for a share class that is not unitised; zero at the fund&#39;s first valuation point.
    label: "...",  // optional — A display label for the node: the fund&#39;s display name on the fund node, the share class&#39;s name on a share class node.
    previousNav: 0.0d,  // optional — The net asset value this node carried at the previous valuation point, in the fund currency. Zero at the fund&#39;s first valuation point.
    netDealingUnits: 0.0d,  // optional — The net units dealt for the share class over the period, so that the shares in issue are the previous shares in issue plus this. Omitted on the fund node and where the bucket set is not unitised.
    shareClassDetails: new BucketSetShareClassDetails(...),  // optional
    navShareClassCurrency: 0.0d,  // optional — The node&#39;s net asset value restated in the share class&#39; own currency, at the rate this node publishes. Set only on share class nodes.
    shareClassToFundFxRate: 0.0d,  // optional — The fx rate from the share class currency to the fund currency at this valuation point. Nav and the bucket values are in the fund currency, so divide by this rate to restate them in the share class currency. Set only on share class nodes.
    previousNavShareClassCurrency: 0.0d  // optional — The net asset value in the share class&#39; currency at the previous valuation point, as that point published it, at the rate that point struck. Zero at the fund&#39;s first valuation point. Absent (rather than zero) if the previous valuation point predates this field.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketSetNode>(json);
```

- [BucketSetResultBucket](BucketSetResultBucket.md) — used in `Buckets`
- [BucketSetShareClassDetails](BucketSetShareClassDetails.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

