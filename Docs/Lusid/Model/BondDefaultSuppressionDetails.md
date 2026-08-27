# Finbourne.Sdk.Lusid.Model.BondDefaultSuppressionDetails

How much of each component of a bond keeps paying after a default, as a fraction from 0.0 (fully  suppressed) to 1.0 (unaffected). An unset field means 1.0. Omitting the whole section is different: that  suppresses coupons and principal outright and leaves interest accruing.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AccrualPercentage** | **decimal?** | Optional | Fraction of the computed accrued interest returned from the default onwards, between 0.0 and 1.0.  Accrued interest supplied through a results store is returned unchanged. Optional, defaulting to 1.0. |
| **CouponPercentage** | **decimal?** | Optional | Fraction of each coupon from the default onwards that is still paid, between 0.0 and 1.0. Optional,  defaulting to 1.0. |
| **PrincipalPercentage** | **decimal?** | Optional | Fraction of each principal repayment from the default onwards still paid, between 0.0 and 1.0.  Optional, defaulting to 1.0. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BondDefaultSuppressionDetails(
    accrualPercentage: 0.0d,  // optional — Fraction of the computed accrued interest returned from the default onwards, between 0.0 and 1.0.  Accrued interest supplied through a results store is returned unchanged. Optional, defaulting to 1.0.
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

