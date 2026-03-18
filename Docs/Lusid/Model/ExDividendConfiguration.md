# Finbourne.Sdk.Lusid.Model.ExDividendConfiguration

Configure the ex-dividend periods for the instrument.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **UseBusinessDays** | **bool** | Optional | Is the ex-dividend period counted in business days or calendar days.  Defaults to false if not set. |
| **ExDividendDays** | **int** | Required | Number of days in the ex-dividend period.  If the settlement date falls in the ex-dividend period then the coupon paid is zero and the accrued interest is negative.  If set, this must be a non-negative number.  If not set, or set to 0, than there is no ex-dividend period. |
| **ReturnNegativeAccrued** | **bool** | Optional | Does the accrued interest go negative in the ex-dividend period, or does it go to zero.  Defaults to true if not set. |
| **ApplyThirty360PayDelay** | **bool** | Optional | Set this flag to true if the ex-dividend days represent a pay delay from the accrual end date in calendar  days under the 30/360 day count convention. The typical use case for this flag are Mortgage Backed Securities  with pay delay between 1 and 60 days, such as FreddieMac and FannieMae. If this flag is set, the useBusinessDays  setting will be ignored.  Defaults to false if not provided. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ExDividendConfiguration(
    useBusinessDays: true,  // optional — Is the ex-dividend period counted in business days or calendar days.  Defaults to false if not set.
    exDividendDays: 0,  // required — Number of days in the ex-dividend period.  If the settlement date falls in the ex-dividend period then the coupon paid is zero and the accrued interest is negative.  If set, this must be a non-negative number.  If not set, or set to 0, than there is no ex-dividend period.
    returnNegativeAccrued: true,  // optional — Does the accrued interest go negative in the ex-dividend period, or does it go to zero.  Defaults to true if not set.
    applyThirty360PayDelay: true  // optional — Set this flag to true if the ex-dividend days represent a pay delay from the accrual end date in calendar  days under the 30/360 day count convention. The typical use case for this flag are Mortgage Backed Securities  with pay delay between 1 and 60 days, such as FreddieMac and FannieMae. If this flag is set, the useBusinessDays  setting will be ignored.  Defaults to false if not provided.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExDividendConfiguration>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

