# Finbourne.Sdk.Lusid.Model.BucketSetResult

A valuation point's results for one bucket set: whether the set is the apportionment set, and its per-node  (fund and share class) buckets and NAV. Allocation-group nodes are not included here - they are surfaced via  the apportionment results.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **IsApportionment** | **bool** | Required | Whether this bucket set is the apportionment set (apportioning non-class-specific P&amp;L across share classes). |
| **Nodes** | [List&lt;BucketSetNode&gt;](BucketSetNode.md) | Required | The nodes making up the bucket set: the fund aggregate and one per share class. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketSetResult(
    isApportionment: true,  // required — Whether this bucket set is the apportionment set (apportioning non-class-specific P&amp;L across share classes).
    nodes: new List<BucketSetNode>()  // required — The nodes making up the bucket set: the fund aggregate and one per share class.
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

