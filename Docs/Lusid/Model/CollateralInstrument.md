# Finbourne.Sdk.Lusid.Model.CollateralInstrument

Wrapper for one instrument in a larger collateral basket, as part of a repurchase agreement modelled as a FlexibleRepo.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Units** | **decimal** | Required | The amount of the instrument in the basket for this repurchase agreement. |
| **Instrument** | [MasteredInstrument](MasteredInstrument.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CollateralInstrument(
    units: 0.0d,  // required — The amount of the instrument in the basket for this repurchase agreement.
    instrument: new MasteredInstrument(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CollateralInstrument>(json);
```

- [MasteredInstrument](MasteredInstrument.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

