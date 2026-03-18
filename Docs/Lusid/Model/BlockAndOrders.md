# Finbourne.Sdk.Lusid.Model.BlockAndOrders

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Block** | [Block](Block.md) | Required | *No description available.* |
| **Orders** | [List&lt;Order&gt;](Order.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BlockAndOrders(
    block: new Block(...),  // required
    orders: new List<Order>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BlockAndOrders>(json);
```


## Related Models

- [Block](Block.md)
- [Order](Order.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

