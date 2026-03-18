# Finbourne.Sdk.Lusid.Model.QuoteAccessMetadataRuleId

An identifier that uniquely identifies a set of Quote access control metadata.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Provider** | **string** | Optional | The platform or vendor that provided the quote. The available values are: Client, DataScope, Lusid, Edi, TraderMade, FactSet, SIX, Bloomberg, Rimes, ICE, LSEG |
| **PriceSource** | **string** | Optional | The source or originator of the quote, e.g. a bank or financial institution. |
| **InstrumentId** | **string** | Optional | The value of the instrument identifier that uniquely identifies the instrument that the quote is for, e.g. &#39;BBG00JX0P539&#39;. |
| **InstrumentIdType** | **string** | Optional | The type of instrument identifier used to uniquely identify the instrument that the quote is for, e.g. &#39;Figi&#39;. |
| **QuoteType** | **string** | Optional | The type of the quote. This allows for quotes other than prices e.g. rates or spreads to be used. |
| **Field** | **string** | Optional | The field of the quote e.g. bid, mid, ask etc. This should be consistent across a time series of quotes. The allowed values depend on the provider according to the following rules: Client : *Any value is accepted*; DataScope : &#39;bid&#39;, &#39;mid&#39;, &#39;ask&#39;; Lusid : *Any value is accepted*; Edi : &#39;bid&#39;, &#39;mid&#39;, &#39;ask&#39;, &#39;open&#39;, &#39;close&#39;, &#39;last&#39;; TraderMade : &#39;bid&#39;, &#39;mid&#39;, &#39;ask&#39;, &#39;open&#39;, &#39;close&#39;, &#39;high&#39;, &#39;low&#39;; FactSet : &#39;bid&#39;, &#39;mid&#39;, &#39;ask&#39;, &#39;open&#39;, &#39;close&#39;; SIX : &#39;bid&#39;, &#39;mid&#39;, &#39;ask&#39;, &#39;open&#39;, &#39;close&#39;, &#39;last&#39;, &#39;referencePrice&#39;, &#39;highPrice&#39;, &#39;lowPrice&#39;, &#39;maxRedemptionPrice&#39;, &#39;maxSubscriptionPrice&#39;, &#39;openPrice&#39;, &#39;bestBidPrice&#39;, &#39;lastBidPrice&#39;, &#39;bestAskPrice&#39;, &#39;lastAskPrice&#39;, &#39;finalSettlementOptions&#39;, &#39;finalSettlementFutures&#39;, &#39;valuationPriceAmount&#39;; Bloomberg : &#39;bid&#39;, &#39;mid&#39;, &#39;ask&#39;, &#39;open&#39;, &#39;close&#39;, &#39;last&#39;; Rimes : &#39;bid&#39;, &#39;mid&#39;, &#39;ask&#39;, &#39;open&#39;, &#39;close&#39;, &#39;last&#39;; ICE : &#39;ask&#39;, &#39;bid&#39;, &#39;close&#39;, &#39;high&#39;, &#39;low&#39;, &#39;open&#39;, &#39;primaryExchangeTradePrice&#39;, &#39;vwap&#39;, &#39;mid&#39;; LSEG : &#39;ASK&#39;, &#39;BID&#39;, &#39;MID_PRICE&#39; |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QuoteAccessMetadataRuleId(
    provider: "...",  // optional — The platform or vendor that provided the quote. The available values are: Client, DataScope, Lusid, Edi, TraderMade, FactSet, SIX, Bloomberg, Rimes, ICE, LSEG
    priceSource: "...",  // optional — The source or originator of the quote, e.g. a bank or financial institution.
    instrumentId: "...",  // optional — The value of the instrument identifier that uniquely identifies the instrument that the quote is for, e.g. &#39;BBG00JX0P539&#39;.
    instrumentIdType: "...",  // optional — The type of instrument identifier used to uniquely identify the instrument that the quote is for, e.g. &#39;Figi&#39;.
    quoteType: "...",  // optional — The type of the quote. This allows for quotes other than prices e.g. rates or spreads to be used.
    field: "..."  // optional — The field of the quote e.g. bid, mid, ask etc. This should be consistent across a time series of quotes. The allowed values depend on the provider according to the following rules: Client : *Any value is accepted*; DataScope : &#39;bid&#39;, &#39;mid&#39;, &#39;ask&#39;; Lusid : *Any value is accepted*; Edi : &#39;bid&#39;, &#39;mid&#39;, &#39;ask&#39;, &#39;open&#39;, &#39;close&#39;, &#39;last&#39;; TraderMade : &#39;bid&#39;, &#39;mid&#39;, &#39;ask&#39;, &#39;open&#39;, &#39;close&#39;, &#39;high&#39;, &#39;low&#39;; FactSet : &#39;bid&#39;, &#39;mid&#39;, &#39;ask&#39;, &#39;open&#39;, &#39;close&#39;; SIX : &#39;bid&#39;, &#39;mid&#39;, &#39;ask&#39;, &#39;open&#39;, &#39;close&#39;, &#39;last&#39;, &#39;referencePrice&#39;, &#39;highPrice&#39;, &#39;lowPrice&#39;, &#39;maxRedemptionPrice&#39;, &#39;maxSubscriptionPrice&#39;, &#39;openPrice&#39;, &#39;bestBidPrice&#39;, &#39;lastBidPrice&#39;, &#39;bestAskPrice&#39;, &#39;lastAskPrice&#39;, &#39;finalSettlementOptions&#39;, &#39;finalSettlementFutures&#39;, &#39;valuationPriceAmount&#39;; Bloomberg : &#39;bid&#39;, &#39;mid&#39;, &#39;ask&#39;, &#39;open&#39;, &#39;close&#39;, &#39;last&#39;; Rimes : &#39;bid&#39;, &#39;mid&#39;, &#39;ask&#39;, &#39;open&#39;, &#39;close&#39;, &#39;last&#39;; ICE : &#39;ask&#39;, &#39;bid&#39;, &#39;close&#39;, &#39;high&#39;, &#39;low&#39;, &#39;open&#39;, &#39;primaryExchangeTradePrice&#39;, &#39;vwap&#39;, &#39;mid&#39;; LSEG : &#39;ASK&#39;, &#39;BID&#39;, &#39;MID_PRICE&#39;
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QuoteAccessMetadataRuleId>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

