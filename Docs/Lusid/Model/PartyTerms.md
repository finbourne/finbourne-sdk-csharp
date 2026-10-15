# Finbourne.Sdk.Lusid.Model.PartyTerms

What one party posts under a margin item.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Threshold** | **decimal?** | Optional | The exposure that is tolerated before margin is called. Empty means no threshold. |
| **IndependentAmount** | **decimal** | Required | The independent amount posted in addition to variation margin. |
| **CashInterest** | [CashInterest](CashInterest.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartyTerms(
    threshold: 0.0d,  // optional — The exposure that is tolerated before margin is called. Empty means no threshold.
    independentAmount: 0.0d,  // required — The independent amount posted in addition to variation margin.
    cashInterest: new CashInterest(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartyTerms>(json);
```

- [CashInterest](CashInterest.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

