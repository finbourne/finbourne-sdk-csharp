# Finbourne.Sdk.Lusid.Model.CancelledOrderResult

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OrderState** | [Order](Order.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CancelledOrderResult(
    orderState: new Order(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CancelledOrderResult>(json);
```


## Related Models

- [Order](Order.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

