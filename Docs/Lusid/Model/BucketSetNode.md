# Finbourne.Sdk.Lusid.Model.BucketSetNode

One node within a bucket set result: the fund aggregate or a single share class. Both carry NAV and buckets; the  capital ratio, the unit counts and the per-unit values are set only on share class nodes.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NodeType** | **string** | Required | The kind of node: the fund aggregate or a single share class. Available values: Fund, Class. |
| **ShareClassShortCode** | **string** | Optional | The short code of the share class this node is for, or null for the fund node. |
| **Nav** | **decimal?** | Optional | The net asset value at this node, in the fund currency, or null where it does not apply to the node type. |
| **CapitalRatio** | **decimal?** | Optional | The share class&#39;s capital ratio (its share of the fund NAV), set only on share class nodes. |
| **Buckets** | [List&lt;BucketSetResultBucket&gt;](BucketSetResultBucket.md) | Required | The buckets on this node, each with its period movement and cumulative values. |
| **PerUnitValue** | **decimal?** | Optional | The share class&#39;s NAV per unit in issue, in the fund currency, rounded to the share class&#39;s PricePrecision (left unrounded where the share class declares none). Reported only for a share class that is unitised and has units in issue to divide by. The dealing price - in the share class currency, with its instrument&#39;s rounding convention applied - is on the share class breakdown&#39;s unitisation data. |
| **SharesInIssue** | **decimal?** | Optional | The share class&#39;s units in issue at the end of the period. Reported only for a share class that is unitised. |
| **PreviousPerUnitValue** | **decimal?** | Optional | The share class&#39;s NAV per unit at the previous valuation point, on the same basis as PerUnitValue. |
| **PreviousSharesInIssue** | **decimal?** | Optional | The share class&#39;s units in issue at the start of the period. Reported only for a share class that is unitised. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketSetNode(
    nodeType: "...",  // required — The kind of node: the fund aggregate or a single share class. Available values: Fund, Class.
    shareClassShortCode: "...",  // optional — The short code of the share class this node is for, or null for the fund node.
    nav: 0.0d,  // optional — The net asset value at this node, in the fund currency, or null where it does not apply to the node type.
    capitalRatio: 0.0d,  // optional — The share class&#39;s capital ratio (its share of the fund NAV), set only on share class nodes.
    buckets: new List<BucketSetResultBucket>(),  // required — The buckets on this node, each with its period movement and cumulative values.
    perUnitValue: 0.0d,  // optional — The share class&#39;s NAV per unit in issue, in the fund currency, rounded to the share class&#39;s PricePrecision (left unrounded where the share class declares none). Reported only for a share class that is unitised and has units in issue to divide by. The dealing price - in the share class currency, with its instrument&#39;s rounding convention applied - is on the share class breakdown&#39;s unitisation data.
    sharesInIssue: 0.0d,  // optional — The share class&#39;s units in issue at the end of the period. Reported only for a share class that is unitised.
    previousPerUnitValue: 0.0d,  // optional — The share class&#39;s NAV per unit at the previous valuation point, on the same basis as PerUnitValue.
    previousSharesInIssue: 0.0d  // optional — The share class&#39;s units in issue at the start of the period. Reported only for a share class that is unitised.
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


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

