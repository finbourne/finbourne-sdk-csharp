# Finbourne.Sdk.Lusid.Model.PartnershipAccountingConfiguration

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Enabled** | **bool** | Required | *No description available.* |
| **ConfigPack** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **CommitmentCurrencyPolicy** | **string** | Optional | Available values: FundCurrencyOnly, AllowLineCurrency. |
| **RegisterPortfolioGroup** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **CapitalModel** | **string** | Optional | Available values: PartnershipCapitalAccounts, SeriesUnitised. |
| **CapabilityOverrides** | [List&lt;CapabilityOverride&gt;](CapabilityOverride.md) | Optional | *No description available.* |
| **Series** | [SeriesConfiguration](SeriesConfiguration.md) | Optional | *No description available.* |
| **EffectiveCapabilities** | **Dictionary&lt;string, string&gt;** | Optional | Derived on the way out; ignored on the way in. |
| **Presentation** | [PresentationConfiguration](PresentationConfiguration.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnershipAccountingConfiguration(
    enabled: true,  // required
    configPack: new ResourceId(...),  // optional
    commitmentCurrencyPolicy: "...",  // optional — Available values: FundCurrencyOnly, AllowLineCurrency.
    registerPortfolioGroup: new ResourceId(...),  // optional
    capitalModel: "...",  // optional — Available values: PartnershipCapitalAccounts, SeriesUnitised.
    capabilityOverrides: new List<CapabilityOverride>(),  // optional
    series: new SeriesConfiguration(...),  // optional
    effectiveCapabilities: ,  // optional — Derived on the way out; ignored on the way in.
    presentation: new PresentationConfiguration(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnershipAccountingConfiguration>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [CapabilityOverride](CapabilityOverride.md)
- [SeriesConfiguration](SeriesConfiguration.md)
- [PresentationConfiguration](PresentationConfiguration.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

