# Finbourne.Sdk.Lusid.Model.OrderInstruction

Record of an order instruction
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **CreatedDate** | **DateTimeOffset** | Required | The active date of this order instruction. |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Client-defined properties associated with this execution. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | The instrument ordered. |
| **Quantity** | **decimal?** | Optional | The quantity of given instrument ordered. |
| **Weight** | **decimal?** | Optional | The proportion of the total portfolio value ordered for the given instrument ordered. |
| **Price** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **InstrumentScope** | **string** | Optional | The scope in which the instrument lies |
| **LusidInstrumentId** | **string** | Optional | The LUSID instrument id for the instrument ordered. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **DataModelMembership** | [DataModelMembership](DataModelMembership.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderInstruction(
    id: new ResourceId(...),  // required
    createdDate: DateTimeOffset.Now,  // required — The active date of this order instruction.
    properties: new PerpetualProperty(...),  // optional — Client-defined properties associated with this execution.
    portfolioId: new ResourceId(...),  // optional
    instrumentIdentifiers: ,  // required — The instrument ordered.
    quantity: 0.0d,  // optional — The quantity of given instrument ordered.
    weight: 0.0d,  // optional — The proportion of the total portfolio value ordered for the given instrument ordered.
    price: new CurrencyAndAmount(...),  // optional
    instrumentScope: "...",  // optional — The scope in which the instrument lies
    lusidInstrumentId: "...",  // optional — The LUSID instrument id for the instrument ordered.
    varVersion: new ModelVersion(...),  // optional
    dataModelMembership: new DataModelMembership(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderInstruction>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [ResourceId](ResourceId.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [ModelVersion](ModelVersion.md)
- [DataModelMembership](DataModelMembership.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

