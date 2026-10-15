# Finbourne.Sdk.Lusid.Model.CarryAccrualAmount

A partner's carry to date as produced by the waterfall.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Required | The investor record the amount belongs to. |
| **CarryToDate** | **decimal** | Required | The cumulative carry the partner has earned to the period end. |
| **ByTier** | [List&lt;CarryTierAmount&gt;](CarryTierAmount.md) | Optional | The carry by waterfall tier. |
| **ClawbackExposure** | **decimal** | Optional | The carry that would have to be returned if the fund liquidated at the period end. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CarryAccrualAmount(
    investorRecordId: "...",  // required — The investor record the amount belongs to.
    carryToDate: 0.0d,  // required — The cumulative carry the partner has earned to the period end.
    byTier: new List<CarryTierAmount>(),  // optional — The carry by waterfall tier.
    clawbackExposure: 0.0d  // optional — The carry that would have to be returned if the fund liquidated at the period end.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CarryAccrualAmount>(json);
```

- [CarryTierAmount](CarryTierAmount.md) — used in `ByTier`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

