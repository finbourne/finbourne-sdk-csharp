# Finbourne.Sdk.Lusid.Model.BondDefaultSuppressionDetails

Which parts of the instrument the default suspends, and by what fraction: 0.0 is fully suppressed and 1.0  unaffected, applying from the default's effective date onwards. An empty block suppresses nothing - every  unset field means 1.0. Omitting the block entirely is different: that cancels coupons and principal  outright from the default onwards, while interest keeps accruing.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AccrualPercentage** | **decimal?** | Optional | Fraction of interest accruing from the default&#39;s effective date onwards, between 0.0 and 1.0. Interest  accrued before that date is unaffected, and a later default restates the fraction from its own date.  Accrued interest supplied through a results store is returned unchanged. Optional, defaulting to 1.0. |
| **CouponPercentage** | **decimal?** | Optional | Fraction of each coupon from the default onwards that is still paid, between 0.0 and 1.0. Optional,  defaulting to 1.0. |
| **PrincipalPercentage** | **decimal?** | Optional | Fraction of each principal repayment from the default onwards still paid, between 0.0 and 1.0.  Optional, defaulting to 1.0. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BondDefaultSuppressionDetails(
    accrualPercentage: 0.0d,  // optional — Fraction of interest accruing from the default&#39;s effective date onwards, between 0.0 and 1.0. Interest  accrued before that date is unaffected, and a later default restates the fraction from its own date.  Accrued interest supplied through a results store is returned unchanged. Optional, defaulting to 1.0.
    couponPercentage: 0.0d,  // optional — Fraction of each coupon from the default onwards that is still paid, between 0.0 and 1.0. Optional,  defaulting to 1.0.
    principalPercentage: 0.0d  // optional — Fraction of each principal repayment from the default onwards still paid, between 0.0 and 1.0.  Optional, defaulting to 1.0.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BondDefaultSuppressionDetails>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

