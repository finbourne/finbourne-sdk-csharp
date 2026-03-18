# Finbourne.Sdk.Lusid.Model.MovedOrderToDifferentBlockResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DestinationBlock** | [Block](Block.md) | Optional | *No description available.* |
| **Order** | [Order](Order.md) | Optional | *No description available.* |
| **SourceBlockId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MovedOrderToDifferentBlockResponse(
    destinationBlock: new Block(...),  // optional
    order: new Order(...),  // optional
    sourceBlockId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MovedOrderToDifferentBlockResponse>(json);
```


## Related Models

- [Block](Block.md)
- [Order](Order.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

