# Finbourne.Sdk.Lusid.Model.BucketSetNode

One node within a bucket set result: the fund aggregate or a single share class. Both carry NAV and buckets; the  capital ratio is set only on share class nodes.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NodeType** | **string** | Required | The kind of node: the fund aggregate or a single share class. Available values: Fund, Class. |
| **ShareClassShortCode** | **string** | Optional | The short code of the share class this node is for, or null for the fund node. |
| **Nav** | **decimal?** | Optional | The net asset value at this node, in the fund currency, or null where it does not apply to the node type. |
| **CapitalRatio** | **decimal?** | Optional | The share class&#39;s capital ratio (its share of the fund NAV), set only on share class nodes. |
| **Buckets** | [List&lt;BucketSetResultBucket&gt;](BucketSetResultBucket.md) | Required | The buckets on this node, each with its period movement and cumulative values. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketSetNode(
    nodeType: "...",  // required — The kind of node: the fund aggregate or a single share class. Available values: Fund, Class.
    shareClassShortCode: "...",  // optional — The short code of the share class this node is for, or null for the fund node.
    nav: 0.0d,  // optional — The net asset value at this node, in the fund currency, or null where it does not apply to the node type.
    capitalRatio: 0.0d,  // optional — The share class&#39;s capital ratio (its share of the fund NAV), set only on share class nodes.
    buckets: new List<BucketSetResultBucket>()  // required — The buckets on this node, each with its period movement and cumulative values.
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

