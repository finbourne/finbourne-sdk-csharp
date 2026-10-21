# Finbourne.Sdk.Lusid.Model.WithholdingTaxReliefAtSourceFlags

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TreatyRas** | **bool** | Required | Whether relief at source applies at the treaty rate. |
| **BetterRas** | **bool** | Required | Whether relief at source applies at the better rate. |
| **EnhancedRas** | **bool** | Required | Whether relief at source applies at the enhanced rate. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WithholdingTaxReliefAtSourceFlags(
    treatyRas: true,  // required — Whether relief at source applies at the treaty rate.
    betterRas: true,  // required — Whether relief at source applies at the better rate.
    enhancedRas: true  // required — Whether relief at source applies at the enhanced rate.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WithholdingTaxReliefAtSourceFlags>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

