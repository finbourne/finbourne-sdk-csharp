# Finbourne.Sdk.Lusid.Model.AllocationEventComponent

One component of an Allocation Event: a part of the amount shared on its own basis and booked to its own slot.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Component** | **string** | Required | The component. For a CapitalCall one of Investment, MgmtFee, OtherFee, PartnershipExpense, OrgCost, Recall, EqualisationInterest or LatePaymentInterest; for a Distribution one of ROC, RealisedGain, Dividend, Interest, OtherIncome, CarryPaid, Withholding or ReturnOfExcess. |
| **Amount** | **decimal** | Required | The part of the event amount this component carries, in the event currency. May be zero, in which case the component allocates nothing. |
| **OriginMemberShortCode** | **string** | Optional | The member of the structure the component originates from, for a basis measured per deal such as PaidInForDeal. Absent means the map&#39;s own member. |
| **WaterfallTier** | **string** | Optional | For a distribution component, the tier of the waterfall it was paid under: ReturnOfContributions, PreferredReturn, CatchUp, CarriedInterest or Residual. |
| **TaxCharacter** | **string** | Optional | For a distribution component, the tax character of the amount: ROC, Gain, Income or Deemed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventComponent(
    component: "...",  // required — The component. For a CapitalCall one of Investment, MgmtFee, OtherFee, PartnershipExpense, OrgCost, Recall, EqualisationInterest or LatePaymentInterest; for a Distribution one of ROC, RealisedGain, Dividend, Interest, OtherIncome, CarryPaid, Withholding or ReturnOfExcess.
    amount: 0.0d,  // required — The part of the event amount this component carries, in the event currency. May be zero, in which case the component allocates nothing.
    originMemberShortCode: "...",  // optional — The member of the structure the component originates from, for a basis measured per deal such as PaidInForDeal. Absent means the map&#39;s own member.
    waterfallTier: "...",  // optional — For a distribution component, the tier of the waterfall it was paid under: ReturnOfContributions, PreferredReturn, CatchUp, CarriedInterest or Residual.
    taxCharacter: "..."  // optional — For a distribution component, the tax character of the amount: ROC, Gain, Income or Deemed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventComponent>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

