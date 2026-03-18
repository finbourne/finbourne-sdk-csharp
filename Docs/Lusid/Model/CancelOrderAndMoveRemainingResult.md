# Finbourne.Sdk.Lusid.Model.CancelOrderAndMoveRemainingResult

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CancelledOrder** | [Order](Order.md) | Optional | *No description available.* |
| **NewOrder** | [Order](Order.md) | Optional | *No description available.* |
| **NewBlockId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CancelOrderAndMoveRemainingResult(
    cancelledOrder: new Order(...),  // optional
    newOrder: new Order(...),  // optional
    newBlockId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CancelOrderAndMoveRemainingResult>(json);
```


## Related Models

- [Order](Order.md)
- [Order](Order.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

