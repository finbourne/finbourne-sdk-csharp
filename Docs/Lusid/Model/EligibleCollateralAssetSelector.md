# Finbourne.Sdk.Lusid.Model.EligibleCollateralAssetSelector

The assets an eligible collateral row applies to, as stored on a schedule.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Kind** | **string** | Required | What the selector matches. One of BaseCurrencyCash, Cash or Instrument. Available values: BaseCurrencyCash, Cash, Instrument. |
| **Currency** | **string** | Optional | The currency of the cash. Required for a Cash selector and not allowed otherwise. |
| **InstrumentFilter** | **string** | Optional | A filter selecting the instruments. Required for an Instrument selector and not allowed otherwise. Checked for structure only when the schedule is stored. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EligibleCollateralAssetSelector(
    kind: "...",  // required — What the selector matches. One of BaseCurrencyCash, Cash or Instrument. Available values: BaseCurrencyCash, Cash, Instrument.
    currency: "...",  // optional — The currency of the cash. Required for a Cash selector and not allowed otherwise.
    instrumentFilter: "..."  // optional — A filter selecting the instruments. Required for an Instrument selector and not allowed otherwise. Checked for structure only when the schedule is stored.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EligibleCollateralAssetSelector>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

