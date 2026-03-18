# Finbourne.Sdk.Lusid.Model.ExchangeTradedOptionContractDetails

Most, if not all, information about contracts is standardised. See, e.g. https://www.cmegroup.com/ for  common codes and similar data. This appears to be in common use by well known market information providers, e.g. Bloomberg and Refinitiv.  There is a lot of overlap with this and FuturesContractDetails but as that is an established DTO we must duplicate a number of fields here
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DomCcy** | **string** | Required | Currency in which the contract is paid. |
| **Strike** | **decimal** | Required | The option strike, this can be negative for some options. |
| **ContractSize** | **decimal** | Required | Size of a single contract. By default this should be set to 1000 if otherwise unknown and is defaulted to such. |
| **Country** | **string** | Required | Country (code) for the exchange. |
| **DeliveryType** | **string** | Required | The delivery type, cash or physical. An option on a future is physically settled if upon exercising the  holder receives a future.    Supported string (enumeration) values are: [Cash, Physical]. |
| **Description** | **string** | Required | Description of contract |
| **ExchangeCode** | **string** | Required | Exchange code for contract. This can be any string to uniquely identify the exchange (e.g. Exchange Name, MIC, BBG code). |
| **ExerciseDate** | **DateTimeOffset** | Required | The last exercise date of the option. |
| **ExerciseType** | **string** | Required | The exercise type, European, American or Bermudan.    Supported string (enumeration) values are: [European, Bermudan, American]. |
| **OptionCode** | **string** | Required | Option Contract Code, typically one or two letters, e.g. OG &#x3D;&gt; Option on Gold. |
| **OptionType** | **string** | Required | The option type, Call or Put.    Supported string (enumeration) values are: [Call, Put]. |
| **Underlying** | [LusidInstrument](LusidInstrument.md) | Required | *No description available.* |
| **UnderlyingCode** | **string** | Required | Code of the underlying, for an option on futures this should be the futures code. |
| **DeliveryDays** | **int** | Optional | Number of business days between exercise date and settlement of the option payoff or underlying.  Defaults to 0 if not set. |
| **BusinessDayConvention** | **string** | Optional | The adjustment type to apply to dates that fall upon a non-business day, e.g. modified following or following.  Supported string (enumeration) values are: [NoAdjustment, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest].  Defaults to \&quot;F\&quot; if not set. |
| **SettlementCalendars** | **List&lt;string&gt;** | Optional | An array of strings denoting calendars used in calculating the option settlement date. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ExchangeTradedOptionContractDetails(
    domCcy: "...",  // required — Currency in which the contract is paid.
    strike: 0.0d,  // required — The option strike, this can be negative for some options.
    contractSize: 0.0d,  // required — Size of a single contract. By default this should be set to 1000 if otherwise unknown and is defaulted to such.
    country: "...",  // required — Country (code) for the exchange.
    deliveryType: "...",  // required — The delivery type, cash or physical. An option on a future is physically settled if upon exercising the  holder receives a future.    Supported string (enumeration) values are: [Cash, Physical].
    description: "...",  // required — Description of contract
    exchangeCode: "...",  // required — Exchange code for contract. This can be any string to uniquely identify the exchange (e.g. Exchange Name, MIC, BBG code).
    exerciseDate: DateTimeOffset.Now,  // required — The last exercise date of the option.
    exerciseType: "...",  // required — The exercise type, European, American or Bermudan.    Supported string (enumeration) values are: [European, Bermudan, American].
    optionCode: "...",  // required — Option Contract Code, typically one or two letters, e.g. OG &#x3D;&gt; Option on Gold.
    optionType: "...",  // required — The option type, Call or Put.    Supported string (enumeration) values are: [Call, Put].
    underlying: new LusidInstrument(...),  // required
    underlyingCode: "...",  // required — Code of the underlying, for an option on futures this should be the futures code.
    deliveryDays: 0,  // optional — Number of business days between exercise date and settlement of the option payoff or underlying.  Defaults to 0 if not set.
    businessDayConvention: "...",  // optional — The adjustment type to apply to dates that fall upon a non-business day, e.g. modified following or following.  Supported string (enumeration) values are: [NoAdjustment, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest].  Defaults to \&quot;F\&quot; if not set.
    settlementCalendars:   // optional — An array of strings denoting calendars used in calculating the option settlement date.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExchangeTradedOptionContractDetails>(json);
```

- [LusidInstrument](LusidInstrument.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

