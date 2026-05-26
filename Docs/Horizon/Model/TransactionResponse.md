# Finbourne.Sdk.Horizon.Model.TransactionResponse

Response containing details of a single transaction for a run.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionId** | **string** | Required | *No description available.* |
| **PublicationStatus** | **string** | Required | *No description available.* |
| **PortfolioScope** | **string** | Optional | *No description available.* |
| **PortfolioCode** | **string** | Optional | *No description available.* |
| **InstrumentId** | **string** | Required | *No description available.* |
| **InstrumentType** | **string** | Required | *No description available.* |
| **InstrumentName** | **string** | Required | *No description available.* |
| **TradeDate** | **DateTimeOffset** | Required | *No description available.* |
| **SettlementDate** | **DateTimeOffset** | Required | *No description available.* |
| **Status** | **string** | Required | *No description available.* |
| **SkipReason** | **string** | Optional | *No description available.* |
| **FailureReason** | **string** | Optional | *No description available.* |
| **OutputFileName** | **string** | Optional | *No description available.* |
| **SentAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **Destinations** | [List&lt;DestinationResponse&gt;](DestinationResponse.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new TransactionResponse(
    transactionId: "...",  // required
    publicationStatus: "...",  // required
    portfolioScope: "...",  // optional
    portfolioCode: "...",  // optional
    instrumentId: "...",  // required
    instrumentType: "...",  // required
    instrumentName: "...",  // required
    tradeDate: DateTimeOffset.Now,  // required
    settlementDate: DateTimeOffset.Now,  // required
    status: "...",  // required
    skipReason: "...",  // optional
    failureReason: "...",  // optional
    outputFileName: "...",  // optional
    sentAt: DateTimeOffset.Now,  // optional
    destinations: new List<DestinationResponse>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionResponse>(json);
```

- [DestinationResponse](DestinationResponse.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

