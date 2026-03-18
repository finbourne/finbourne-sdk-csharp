# Finbourne.Sdk.Lusid.Model.Compounding

The compounding settings used on interest rate.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AveragingMethod** | **string** | Optional | Defines whether a weighted or unweighted average is used when calculating the average rate.  It applies only when CompoundingMethod &#x3D; ‘Averaging‘.    Supported string (enumeration) values are: [Unweighted, UnweightedIncludingWeekends, Weighted].  Defaults to \&quot;None\&quot; if not set. |
| **CalculationShiftMethod** | **string** | Optional | Defines which resets and day counts are used for the rate calculation    Supported string (enumeration) values are: [Lookback, NoShift, ObservationPeriodShift, Lockout].  Defaults to \&quot;NoShift\&quot; if not set. |
| **CompoundingMethod** | **string** | Required | If the interest rate is simple, compounded or using a pre-computed compounded index.    Supported string (enumeration) values are: [Averaging, Compounding, CompoundedIndex, NonCumulativeCompounding]. |
| **ResetFrequency** | **string** | Required | The interest payment frequency.    For more information on tenors, see [knowledge base article KA-02097](https://support.lusid.com/knowledgebase/article/KA-02097) |
| **Shift** | **int** | Optional | Defines the number of days to lockout or shift observation period by - should be a non-negative integer.  Defaults to 0 if not set. |
| **SpreadCompoundingMethod** | **string** | Optional | Defines how the computed leg spread is applied to compounded rate.  It applies only when CompoundingMethod &#x3D; ‘Compounding‘ or ‘CompoundedIndex‘.    Available compounding methods:    | Method | Description |  | - -- -- - | - -- -- -- -- -- |  | Straight | Compounding rate in each compound period includes the spread. |  | Flat | Compounding rate does not include the spread, and the spread is used for simple interest in each compound period. |  | SpreadExclusive | Compounding rate does not include the spread, and the spread is used for simple interest for whole accrual period. |    The values \&quot;IsdaCompounding\&quot;, \&quot;NoCompounding\&quot;, \&quot;IsdaFlatCompounding\&quot;, and \&quot;None\&quot; are accepted for compatibility  with existing instruments and their use is discouraged.    Supported string (enumeration) values are: [Straight, IsdaCompounding, NoCompounding, SpreadExclusive, IsdaFlatCompounding, Flat, None].  Defaults to \&quot;None\&quot; if not set. |
| **RoundingPrecision** | **int?** | Optional | Defines the number of decimal places the compounded rate (expressed as a decimal) should be rounded to.  This is an optional field, leaving it blank will mean no rounding takes place in Compounding. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Compounding(
    averagingMethod: "...",  // optional — Defines whether a weighted or unweighted average is used when calculating the average rate.  It applies only when CompoundingMethod &#x3D; ‘Averaging‘.    Supported string (enumeration) values are: [Unweighted, UnweightedIncludingWeekends, Weighted].  Defaults to \&quot;None\&quot; if not set.
    calculationShiftMethod: "...",  // optional — Defines which resets and day counts are used for the rate calculation    Supported string (enumeration) values are: [Lookback, NoShift, ObservationPeriodShift, Lockout].  Defaults to \&quot;NoShift\&quot; if not set.
    compoundingMethod: "...",  // required — If the interest rate is simple, compounded or using a pre-computed compounded index.    Supported string (enumeration) values are: [Averaging, Compounding, CompoundedIndex, NonCumulativeCompounding].
    resetFrequency: "...",  // required — The interest payment frequency.    For more information on tenors, see [knowledge base article KA-02097](https://support.lusid.com/knowledgebase/article/KA-02097)
    shift: 0,  // optional — Defines the number of days to lockout or shift observation period by - should be a non-negative integer.  Defaults to 0 if not set.
    spreadCompoundingMethod: "...",  // optional — Defines how the computed leg spread is applied to compounded rate.  It applies only when CompoundingMethod &#x3D; ‘Compounding‘ or ‘CompoundedIndex‘.    Available compounding methods:    | Method | Description |  | - -- -- - | - -- -- -- -- -- |  | Straight | Compounding rate in each compound period includes the spread. |  | Flat | Compounding rate does not include the spread, and the spread is used for simple interest in each compound period. |  | SpreadExclusive | Compounding rate does not include the spread, and the spread is used for simple interest for whole accrual period. |    The values \&quot;IsdaCompounding\&quot;, \&quot;NoCompounding\&quot;, \&quot;IsdaFlatCompounding\&quot;, and \&quot;None\&quot; are accepted for compatibility  with existing instruments and their use is discouraged.    Supported string (enumeration) values are: [Straight, IsdaCompounding, NoCompounding, SpreadExclusive, IsdaFlatCompounding, Flat, None].  Defaults to \&quot;None\&quot; if not set.
    roundingPrecision: 0  // optional — Defines the number of decimal places the compounded rate (expressed as a decimal) should be rounded to.  This is an optional field, leaving it blank will mean no rounding takes place in Compounding.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Compounding>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

