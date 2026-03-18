# Finbourne.Sdk.Lusid.Model.CdsFlowConventions

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RollFrequency** | **string** | Optional | The frequency at which the reference bonds are updated, this defaults to 6M, but can be 3M, exp for historically issued products.    For more information on tenors, see [knowledge base article KA-02097](https://support.lusid.com/knowledgebase/article/KA-02097) |
| **Currency** | **string** | Required | Currency of the flow convention. |
| **PaymentFrequency** | **string** | Required | When generating a multiperiod flow, or when the maturity of the flow is not given but the start date is,  the tenor is the time-step from the anchor-date to the nominal maturity of the flow prior to any adjustment. |
| **DayCountConvention** | **string** | Required | when calculating the fraction of a year between two dates, what convention is used to represent the number of days in a year  and difference between them.  For more information on day counts, see [knowledge base article KA-01798](https://support.lusid.com/knowledgebase/article/KA-01798)                Supported string (enumeration) values are: [Actual360, Act360, MoneyMarket, Actual365, Act365, Thirty360, ThirtyU360, Bond, ThirtyE360, EuroBond, ActualActual, ActAct, ActActIsda, ActActIsma, ActActIcma, OneOne, Act364, Act365F, Act365L, Act365_25, Act252, Bus252, NL360, NL365, ActActAFB, Act365Cad, ThirtyActIsda, Thirty365Isda, ThirtyEActIsda, ThirtyE360Isda, ThirtyE365Isda, ThirtyU360EOM]. |
| **RollConvention** | **string** | Required | For backward compatibility, this can either specify a business day convention or a roll convention. If the business  day convention is provided using the BusinessDayConvention property, this must be a valid roll convention.                When used as a roll convention:  The conventions specifying the rule used to generate dates in a schedule.    Supported string (enumeration) values are: [None, EndOfMonth, IMM, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, FirstMonday, FirstTuesday, FirstWednesday, FirstThursday, FirstFriday, SecondMonday, SecondTuesday, SecondWednesday, SecondThursday, SecondFriday, ThirdMonday, ThirdTuesday, ThirdWednesday, ThirdThursday, ThirdFriday, FourthMonday, FourthTuesday, FourthWednesday, FourthThursday, FourthFriday, LastMonday, LastTuesday, LastWednesday, LastThursday, LastFriday].                When in backward compatible mode:  Supported string (enumeration) values are: [NoAdjustment, None, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing]. |
| **PaymentCalendars** | **List&lt;string&gt;** | Required | An array of strings denoting holiday calendars that apply to generation of payment schedules. |
| **ResetCalendars** | **List&lt;string&gt;** | Required | An array of strings denoting holiday calendars that apply to generation of reset schedules. |
| **SettleDays** | **int** | Optional | Number of Good Business Days between the trade date and the effective or settlement date of the instrument. Defaults to 0 if not set. |
| **ResetDays** | **int** | Optional | The number of Good Business Days between determination and payment of reset. Defaults to 0 if not set. |
| **BusinessDayConvention** | **string** | Optional | When generating a set of dates, what convention should be used for adjusting dates that coincide with a non-business day.    Supported string (enumeration) values are: [NoAdjustment, None, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest]. |
| **Scope** | **string** | Optional | The scope used when updating or inserting the convention. |
| **Code** | **string** | Optional | The code of the convention. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CdsFlowConventions(
    rollFrequency: "...",  // optional — The frequency at which the reference bonds are updated, this defaults to 6M, but can be 3M, exp for historically issued products.    For more information on tenors, see [knowledge base article KA-02097](https://support.lusid.com/knowledgebase/article/KA-02097)
    currency: "...",  // required — Currency of the flow convention.
    paymentFrequency: "...",  // required — When generating a multiperiod flow, or when the maturity of the flow is not given but the start date is,  the tenor is the time-step from the anchor-date to the nominal maturity of the flow prior to any adjustment.
    dayCountConvention: "...",  // required — when calculating the fraction of a year between two dates, what convention is used to represent the number of days in a year  and difference between them.  For more information on day counts, see [knowledge base article KA-01798](https://support.lusid.com/knowledgebase/article/KA-01798)                Supported string (enumeration) values are: [Actual360, Act360, MoneyMarket, Actual365, Act365, Thirty360, ThirtyU360, Bond, ThirtyE360, EuroBond, ActualActual, ActAct, ActActIsda, ActActIsma, ActActIcma, OneOne, Act364, Act365F, Act365L, Act365_25, Act252, Bus252, NL360, NL365, ActActAFB, Act365Cad, ThirtyActIsda, Thirty365Isda, ThirtyEActIsda, ThirtyE360Isda, ThirtyE365Isda, ThirtyU360EOM].
    rollConvention: "...",  // required — For backward compatibility, this can either specify a business day convention or a roll convention. If the business  day convention is provided using the BusinessDayConvention property, this must be a valid roll convention.                When used as a roll convention:  The conventions specifying the rule used to generate dates in a schedule.    Supported string (enumeration) values are: [None, EndOfMonth, IMM, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, FirstMonday, FirstTuesday, FirstWednesday, FirstThursday, FirstFriday, SecondMonday, SecondTuesday, SecondWednesday, SecondThursday, SecondFriday, ThirdMonday, ThirdTuesday, ThirdWednesday, ThirdThursday, ThirdFriday, FourthMonday, FourthTuesday, FourthWednesday, FourthThursday, FourthFriday, LastMonday, LastTuesday, LastWednesday, LastThursday, LastFriday].                When in backward compatible mode:  Supported string (enumeration) values are: [NoAdjustment, None, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing].
    paymentCalendars: ,  // required — An array of strings denoting holiday calendars that apply to generation of payment schedules.
    resetCalendars: ,  // required — An array of strings denoting holiday calendars that apply to generation of reset schedules.
    settleDays: 0,  // optional — Number of Good Business Days between the trade date and the effective or settlement date of the instrument. Defaults to 0 if not set.
    resetDays: 0,  // optional — The number of Good Business Days between determination and payment of reset. Defaults to 0 if not set.
    businessDayConvention: "...",  // optional — When generating a set of dates, what convention should be used for adjusting dates that coincide with a non-business day.    Supported string (enumeration) values are: [NoAdjustment, None, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest].
    scope: "...",  // optional — The scope used when updating or inserting the convention.
    code: "..."  // optional — The code of the convention.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CdsFlowConventions>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

