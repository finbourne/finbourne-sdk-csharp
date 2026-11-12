# Finbourne.Sdk.Lusid.Model.PreviewBlocksRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Orders** | [List&lt;OrderRequest&gt;](OrderRequest.md) | Required | The orders to group into blocks. Properties in the Block domain are taken as the block&#39;s properties and form part of the grouping key. |
| **GroupingMode** | **string** | Optional | How orders are grouped. None: one block per order. SameSide: orders sharing instrument, side, type, time in force, price (for Limit and Stop), basis, date and block properties share a block. CrossSide: as SameSide but ignoring side, so opposing orders may net into one block, provided each portfolio&#39;s net for the instrument has the same sign as the block&#39;s first portfolio. Available values: None, SameSide, CrossSide. |
| **BlockId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PreviewBlocksRequest(
    orders: new List<OrderRequest>(),  // required — The orders to group into blocks. Properties in the Block domain are taken as the block&#39;s properties and form part of the grouping key.
    groupingMode: "...",  // optional — How orders are grouped. None: one block per order. SameSide: orders sharing instrument, side, type, time in force, price (for Limit and Stop), basis, date and block properties share a block. CrossSide: as SameSide but ignoring side, so opposing orders may net into one block, provided each portfolio&#39;s net for the instrument has the same sign as the block&#39;s first portfolio. Available values: None, SameSide, CrossSide.
    blockId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PreviewBlocksRequest>(json);
```


## Related Models

- [OrderRequest](OrderRequest.md) — used in `Orders`
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

