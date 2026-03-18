# Finbourne.Sdk.Lusid.Model.OrderGraphBlockAllocationDetail

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **AllocatedOrderId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Quantity** | **decimal** | Required | The quantity of this allocation, with direction relative to the containing block. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderGraphBlockAllocationDetail(
    id: new ResourceId(...),  // required
    allocatedOrderId: new ResourceId(...),  // optional
    quantity: 0.0d  // required — The quantity of this allocation, with direction relative to the containing block.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderGraphBlockAllocationDetail>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

