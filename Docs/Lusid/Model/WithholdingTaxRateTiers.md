# Finbourne.Sdk.Lusid.Model.WithholdingTaxRateTiers

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CountryRate** | **decimal** | Required | The statutory rate of the matched row, before relief. |
| **TreatyRate** | **decimal?** | Optional | The treaty rate of the matched row. Null when the tier does not apply. |
| **BetterRate** | **decimal?** | Optional | The better rate of the matched row. Null when the tier does not apply. |
| **EnhancedRate** | **decimal?** | Optional | The enhanced rate of the matched row. Null when the tier does not apply. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WithholdingTaxRateTiers(
    countryRate: 0.0d,  // required — The statutory rate of the matched row, before relief.
    treatyRate: 0.0d,  // optional — The treaty rate of the matched row. Null when the tier does not apply.
    betterRate: 0.0d,  // optional — The better rate of the matched row. Null when the tier does not apply.
    enhancedRate: 0.0d  // optional — The enhanced rate of the matched row. Null when the tier does not apply.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WithholdingTaxRateTiers>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

