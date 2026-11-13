# Finbourne.Sdk.Lusid.Model.CollateralInstrument

Wrapper for one instrument in a larger collateral basket, as part of a repurchase agreement modelled as a FlexibleRepo.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Units** | **decimal** | Required | The amount of the instrument in the basket for this repurchase agreement. |
| **Instrument** | [MasteredInstrument](MasteredInstrument.md) | Required | *No description available.* |
| **CollateralStartDate** | **DateTimeOffset?** | Optional | The date from which the instrument is held as collateral for this repurchase agreement.  Read only: an instrument upsert cannot set or change it. An existing value must be sent back unchanged.  When not set, the instrument is held from the StartDate of the FlexibleRepo. |
| **CollateralEndDate** | **DateTimeOffset?** | Optional | The date on which the instrument stops being held as collateral for this repurchase agreement.  Read only: an instrument upsert cannot set or change it. An existing value must be sent back unchanged.  When not set, the instrument is held until the MaturityDate of the FlexibleRepo. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CollateralInstrument(
    units: 0.0d,  // required — The amount of the instrument in the basket for this repurchase agreement.
    instrument: new MasteredInstrument(...),  // required
    collateralStartDate: DateTimeOffset.Now,  // optional — The date from which the instrument is held as collateral for this repurchase agreement.  Read only: an instrument upsert cannot set or change it. An existing value must be sent back unchanged.  When not set, the instrument is held from the StartDate of the FlexibleRepo.
    collateralEndDate: DateTimeOffset.Now  // optional — The date on which the instrument stops being held as collateral for this repurchase agreement.  Read only: an instrument upsert cannot set or change it. An existing value must be sent back unchanged.  When not set, the instrument is held until the MaturityDate of the FlexibleRepo.
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

