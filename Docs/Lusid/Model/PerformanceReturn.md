# Finbourne.Sdk.Lusid.Model.PerformanceReturn

A list of Returns.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveAt** | **DateTimeOffset** | Required | The effectiveAt for the return. |
| **RateOfReturn** | **decimal** | Required | The return number. |
| **OpeningMarketValue** | **decimal?** | Optional | The opening market value. |
| **ClosingMarketValue** | **decimal?** | Optional | The closing market value. |
| **Period** | **string** | Optional | Upsert the returns on a Daily or Monthly period. Defaults to Daily. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PerformanceReturn(
    effectiveAt: DateTimeOffset.Now,  // required — The effectiveAt for the return.
    rateOfReturn: 0.0d,  // required — The return number.
    openingMarketValue: 0.0d,  // optional — The opening market value.
    closingMarketValue: 0.0d,  // optional — The closing market value.
    period: "..."  // optional — Upsert the returns on a Daily or Monthly period. Defaults to Daily.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PerformanceReturn>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

