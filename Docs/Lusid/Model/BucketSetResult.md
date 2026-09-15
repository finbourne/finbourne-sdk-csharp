# Finbourne.Sdk.Lusid.Model.BucketSetResult

A valuation point's results for one bucket set: whether the set is the apportionment set, and its per-node  (fund and share class) buckets and NAV. Allocation-group nodes are not included here - they are surfaced via  the apportionment results.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BucketSetCode** | **string** | Required | The code of the fund configuration&#39;s bucket set definition these results were produced from. Empty for a fund valued from component filters, which has no bucket set definition to name. |
| **IsApportionment** | **bool** | Required | Whether this bucket set is the apportionment set (apportioning non-class-specific P&amp;L across share classes). |
| **Nodes** | [List&lt;BucketSetNode&gt;](BucketSetNode.md) | Required | The nodes making up the bucket set: the fund aggregate and one per share class. |
| **DisplayName** | **string** | Optional | The display name of the bucket set, as configured on the fund configuration. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketSetResult(
    bucketSetCode: "...",  // required — The code of the fund configuration&#39;s bucket set definition these results were produced from. Empty for a fund valued from component filters, which has no bucket set definition to name.
    isApportionment: true,  // required — Whether this bucket set is the apportionment set (apportioning non-class-specific P&amp;L across share classes).
    nodes: new List<BucketSetNode>(),  // required — The nodes making up the bucket set: the fund aggregate and one per share class.
    displayName: "..."  // optional — The display name of the bucket set, as configured on the fund configuration.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketSetResult>(json);
```

- [BucketSetNode](BucketSetNode.md) — used in `Nodes`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

