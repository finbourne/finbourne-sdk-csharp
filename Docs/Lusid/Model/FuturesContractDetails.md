# Finbourne.Sdk.Lusid.Model.FuturesContractDetails

Most, if not all, information about contracts is standardized. See, e.g. https://www.cmegroup.com/ for  common codes and similar data. This appears to be in common use by well known market information providers, e.g. Bloomberg and Refinitiv.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DomCcy** | **string** | Required | Currency in which the contract is paid. |
| **FgnCcy** | **string** | Optional | Currency of the underlying, for use with FX Futures |
| **AssetClass** | **string** | Optional | The asset class of the underlying. Optional and will default to Unknown if not set.    Supported string (enumeration) values are: [InterestRates, FX, Inflation, Equities, Credit, Commodities, Money]. |
| **ContractCode** | **string** | Required | The contract code used by the exchange, e.g. “CL” for Crude Oil, “ES” for E-mini SP 500, “FGBL” for Bund Futures, etc. |
| **ContractMonth** | **string** | Optional | Which month does the contract trade for.    Supported string (enumeration) values are: [F, G, H, J, K, M, N, Q, U, V, X, Z].  Defaults to \&quot;Unknown\&quot; if not set. |
| **ContractSize** | **decimal** | Required | Size of a single contract. |
| **Convention** | **string** | Optional | If appropriate, the day count convention method used in pricing (rates futures).  For more information on day counts, see [knowledge base article KA-01798](https://support.lusid.com/knowledgebase/article/KA-01798)                Supported string (enumeration) values are: [Actual360, Act360, MoneyMarket, Actual365, Act365, Thirty360, ThirtyU360, Bond, ThirtyE360, EuroBond, ActualActual, ActAct, ActActIsda, ActActIsma, ActActIcma, OneOne, Act364, Act365F, Act365L, Act365_25, Act252, Bus252, NL360, NL365, ActActAFB, Act365Cad, ThirtyActIsda, Thirty365Isda, ThirtyEActIsda, ThirtyE360Isda, ThirtyE365Isda, ThirtyU360EOM]. |
| **Country** | **string** | Optional | Country (code) for the exchange. |
| **Description** | **string** | Optional | Description of contract. |
| **ExchangeCode** | **string** | Required | Exchange code for contract. This can be any string to uniquely identify the exchange (e.g. Exchange Name, MIC, BBG code). |
| **ExchangeName** | **string** | Optional | Exchange name (for when code is not automatically recognised). |
| **TickerStep** | **decimal** | Optional | Minimal step size change in ticker. |
| **UnitValue** | **decimal** | Optional | The value in the currency of a 1 unit change in the contract price. |
| **Calendars** | **List&lt;string&gt;** | Optional | Holiday calendars that apply to yield-to-price conversions (i.e. for BRL futures). |
| **DeliveryType** | **string** | Optional | Delivery type to be used on settling the contract.  Optional: Defaults to DeliveryType.Physical if not provided.    Supported string (enumeration) values are: [Cash, Physical]. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FuturesContractDetails(
    domCcy: "...",  // required — Currency in which the contract is paid.
    fgnCcy: "...",  // optional — Currency of the underlying, for use with FX Futures
    assetClass: "...",  // optional — The asset class of the underlying. Optional and will default to Unknown if not set.    Supported string (enumeration) values are: [InterestRates, FX, Inflation, Equities, Credit, Commodities, Money].
    contractCode: "...",  // required — The contract code used by the exchange, e.g. “CL” for Crude Oil, “ES” for E-mini SP 500, “FGBL” for Bund Futures, etc.
    contractMonth: "...",  // optional — Which month does the contract trade for.    Supported string (enumeration) values are: [F, G, H, J, K, M, N, Q, U, V, X, Z].  Defaults to \&quot;Unknown\&quot; if not set.
    contractSize: 0.0d,  // required — Size of a single contract.
    convention: "...",  // optional — If appropriate, the day count convention method used in pricing (rates futures).  For more information on day counts, see [knowledge base article KA-01798](https://support.lusid.com/knowledgebase/article/KA-01798)                Supported string (enumeration) values are: [Actual360, Act360, MoneyMarket, Actual365, Act365, Thirty360, ThirtyU360, Bond, ThirtyE360, EuroBond, ActualActual, ActAct, ActActIsda, ActActIsma, ActActIcma, OneOne, Act364, Act365F, Act365L, Act365_25, Act252, Bus252, NL360, NL365, ActActAFB, Act365Cad, ThirtyActIsda, Thirty365Isda, ThirtyEActIsda, ThirtyE360Isda, ThirtyE365Isda, ThirtyU360EOM].
    country: "...",  // optional — Country (code) for the exchange.
    description: "...",  // optional — Description of contract.
    exchangeCode: "...",  // required — Exchange code for contract. This can be any string to uniquely identify the exchange (e.g. Exchange Name, MIC, BBG code).
    exchangeName: "...",  // optional — Exchange name (for when code is not automatically recognised).
    tickerStep: 0.0d,  // optional — Minimal step size change in ticker.
    unitValue: 0.0d,  // optional — The value in the currency of a 1 unit change in the contract price.
    calendars: ,  // optional — Holiday calendars that apply to yield-to-price conversions (i.e. for BRL futures).
    deliveryType: "..."  // optional — Delivery type to be used on settling the contract.  Optional: Defaults to DeliveryType.Physical if not provided.    Supported string (enumeration) values are: [Cash, Physical].
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FuturesContractDetails>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

