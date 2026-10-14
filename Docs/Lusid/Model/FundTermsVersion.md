# Finbourne.Sdk.Lusid.Model.FundTermsVersion

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TermsVersionId** | **string** | Required | *No description available.* |
| **EffectiveFrom** | **DateTimeOffset** | Required | *No description available.* |
| **Fees** | [List&lt;FeeDefinition&gt;](FeeDefinition.md) | Optional | *No description available.* |
| **Carry** | [CarryParameters](CarryParameters.md) | Optional | *No description available.* |
| **Recycling** | [RecyclingTerms](RecyclingTerms.md) | Optional | *No description available.* |
| **Equalisation** | [EqualisationTerms](EqualisationTerms.md) | Optional | *No description available.* |
| **AppliesFromClosingId** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundTermsVersion(
    termsVersionId: "...",  // required
    effectiveFrom: DateTimeOffset.Now,  // required
    fees: new List<FeeDefinition>(),  // optional
    carry: new CarryParameters(...),  // optional
    recycling: new RecyclingTerms(...),  // optional
    equalisation: new EqualisationTerms(...),  // optional
    appliesFromClosingId: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundTermsVersion>(json);
```

- [FeeDefinition](FeeDefinition.md)
- [CarryParameters](CarryParameters.md)
- [RecyclingTerms](RecyclingTerms.md)
- [EqualisationTerms](EqualisationTerms.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

