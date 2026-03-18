# Finbourne.Sdk.Lusid.Model.CashElection

Cash election for Events that result in a cash payment.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ElectionKey** | **string** | Required | Unique key used to identify this election. |
| **ExchangeRate** | **decimal?** | Optional | The exchange rate if this is not the declared CashElection.  Defaults to 1 if Election is Declared. |
| **DividendRate** | **decimal?** | Optional | The payment rate for this CashElection. |
| **IsChosen** | **bool** | Optional | Has this election been chosen.  Only one Election may be Chosen per Event. |
| **IsDeclared** | **bool** | Optional | Is this the declared CashElection.  Only one Election may be Declared per Event. |
| **IsDefault** | **bool** | Optional | Is this election the default.  Only one Election may be Default per Event |
| **DividendCurrency** | **string** | Required | The payment currency for this CashElection. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CashElection(
    electionKey: "...",  // required — Unique key used to identify this election.
    exchangeRate: 0.0d,  // optional — The exchange rate if this is not the declared CashElection.  Defaults to 1 if Election is Declared.
    dividendRate: 0.0d,  // optional — The payment rate for this CashElection.
    isChosen: true,  // optional — Has this election been chosen.  Only one Election may be Chosen per Event.
    isDeclared: true,  // optional — Is this the declared CashElection.  Only one Election may be Declared per Event.
    isDefault: true,  // optional — Is this election the default.  Only one Election may be Default per Event
    dividendCurrency: "..."  // required — The payment currency for this CashElection.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CashElection>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

