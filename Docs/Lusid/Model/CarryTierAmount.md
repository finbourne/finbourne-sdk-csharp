# Finbourne.Sdk.Lusid.Model.CarryTierAmount

A partner's carry split by waterfall tier.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Tier** | **string** | Required | The waterfall tier. |
| **Realised** | **decimal** | Required | The carry realised in the tier. |
| **Hypothetical** | **decimal** | Required | The carry the tier would pay if the fund liquidated at the period end. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CarryTierAmount(
    tier: "...",  // required — The waterfall tier.
    realised: 0.0d,  // required — The carry realised in the tier.
    hypothetical: 0.0d  // required — The carry the tier would pay if the fund liquidated at the period end.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CarryTierAmount>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

