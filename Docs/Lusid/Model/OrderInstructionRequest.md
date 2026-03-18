# Finbourne.Sdk.Lusid.Model.OrderInstructionRequest

A request to create or update a Order Instruction.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **CreatedDate** | **DateTimeOffset** | Required | The active date of this order instruction. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Optional | The instrument ordered. |
| **Quantity** | **decimal?** | Optional | The quantity of given instrument ordered. |
| **Weight** | **decimal?** | Optional | The proportion of the total portfolio value ordered for the given instrument ordered. |
| **Price** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Client-defined properties associated with this execution. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderInstructionRequest(
    id: new ResourceId(...),  // required
    createdDate: DateTimeOffset.Now,  // required — The active date of this order instruction.
    portfolioId: new ResourceId(...),  // optional
    instrumentIdentifiers: ,  // optional — The instrument ordered.
    quantity: 0.0d,  // optional — The quantity of given instrument ordered.
    weight: 0.0d,  // optional — The proportion of the total portfolio value ordered for the given instrument ordered.
    price: new CurrencyAndAmount(...),  // optional
    properties: new PerpetualProperty(...)  // optional — Client-defined properties associated with this execution.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderInstructionRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

