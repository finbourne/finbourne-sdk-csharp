# Finbourne.Sdk.Lusid.Model.ReconciliationBreak

A reconciliation break
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentScope** | **string** | Optional | The scope in which the instrument lies. |
| **InstrumentUid** | **string** | Required | Unique instrument identifier |
| **SubHoldingKeys** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Required | Any other properties that comprise the Sub-Holding Key |
| **LeftUnits** | **decimal** | Required | Units from the left hand side |
| **RightUnits** | **decimal** | Required | Units from the right hand side |
| **DifferenceUnits** | **decimal** | Required | Difference in units |
| **LeftCost** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **RightCost** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **DifferenceCost** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **InstrumentProperties** | [List&lt;Property&gt;](Property.md) | Required | Additional features relating to the instrument |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReconciliationBreak(
    instrumentScope: "...",  // optional — The scope in which the instrument lies.
    instrumentUid: "...",  // required — Unique instrument identifier
    subHoldingKeys: new PerpetualProperty(...),  // required — Any other properties that comprise the Sub-Holding Key
    leftUnits: 0.0d,  // required — Units from the left hand side
    rightUnits: 0.0d,  // required — Units from the right hand side
    differenceUnits: 0.0d,  // required — Difference in units
    leftCost: new CurrencyAndAmount(...),  // required
    rightCost: new CurrencyAndAmount(...),  // required
    differenceCost: new CurrencyAndAmount(...),  // required
    instrumentProperties: new List<Property>()  // required — Additional features relating to the instrument
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReconciliationBreak>(json);
```

- [PerpetualProperty](PerpetualProperty.md) — used in `SubHoldingKeys`
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [Property](Property.md) — used in `InstrumentProperties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

