# Finbourne.Sdk.Lusid.Model.SecurityOfferConstituent

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NewInstrument** | [NewInstrument](NewInstrument.md) | Required | *No description available.* |
| **UnitsRatio** | [UnitsRatio](UnitsRatio.md) | Required | *No description available.* |
| **SettlementDate** | **DateTimeOffset** | Required | *No description available.* |
| **MinPieceSize** | **decimal?** | Optional | *No description available.* |
| **MinIncrement** | **decimal?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SecurityOfferConstituent(
    newInstrument: new NewInstrument(...),  // required
    unitsRatio: new UnitsRatio(...),  // required
    settlementDate: DateTimeOffset.Now,  // required
    minPieceSize: 0.0d,  // optional
    minIncrement: 0.0d  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SecurityOfferConstituent>(json);
```


## Related Models

- [NewInstrument](NewInstrument.md)
- [UnitsRatio](UnitsRatio.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

