# Finbourne.Sdk.Lusid.Model.CancelOrdersAndMoveRemainingRequest

A request to create or update a Order.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CancelOrderId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **MoveRemainingToOrderId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **MoveRemainingToBlockId** | [ResourceId](ResourceId.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CancelOrdersAndMoveRemainingRequest(
    cancelOrderId: new ResourceId(...),  // required
    moveRemainingToOrderId: new ResourceId(...),  // required
    moveRemainingToBlockId: new ResourceId(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CancelOrdersAndMoveRemainingRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

