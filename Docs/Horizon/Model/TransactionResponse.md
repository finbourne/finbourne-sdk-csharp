# Finbourne.Sdk.Horizon.Model.TransactionResponse

Response containing details of a single transaction for a run. A transaction built twice in one batch appears once per build. FailureStage says whether a failed transaction failed while being built (Build) or while its file was being delivered (Delivery).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionId** | **string** | Required | *No description available.* |
| **PublicationStatus** | **string** | Required | The outcome the screens show for this row: Sent, Skipped or Failed. |
| **PortfolioScope** | **string** | Optional | *No description available.* |
| **PortfolioCode** | **string** | Optional | *No description available.* |
| **InstrumentId** | **string** | Optional | *No description available.* |
| **InstrumentType** | **string** | Optional | *No description available.* |
| **InstrumentName** | **string** | Optional | *No description available.* |
| **TradeDate** | **DateTimeOffset?** | Optional | *No description available.* |
| **SettlementDate** | **DateTimeOffset?** | Optional | *No description available.* |
| **Status** | **string** | Required | The batch element&#39;s processing state as the worker left it, not the outcome; read PublicationStatus for that. |
| **SkipReason** | **string** | Optional | *No description available.* |
| **FailureReason** | **string** | Optional | *No description available.* |
| **OutputFileName** | **string** | Optional | *No description available.* |
| **SentAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **Destinations** | [List&lt;DestinationResponse&gt;](DestinationResponse.md) | Required | *No description available.* |
| **FailureStage** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new TransactionResponse(
    transactionId: "...",  // required
    publicationStatus: "...",  // required — The outcome the screens show for this row: Sent, Skipped or Failed.
    portfolioScope: "...",  // optional
    portfolioCode: "...",  // optional
    instrumentId: "...",  // optional
    instrumentType: "...",  // optional
    instrumentName: "...",  // optional
    tradeDate: DateTimeOffset.Now,  // optional
    settlementDate: DateTimeOffset.Now,  // optional
    status: "...",  // required — The batch element&#39;s processing state as the worker left it, not the outcome; read PublicationStatus for that.
    skipReason: "...",  // optional
    failureReason: "...",  // optional
    outputFileName: "...",  // optional
    sentAt: DateTimeOffset.Now,  // optional
    destinations: new List<DestinationResponse>(),  // required
    failureStage: "..."  // optional
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

