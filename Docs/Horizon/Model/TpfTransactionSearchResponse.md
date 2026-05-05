# Finbourne.Sdk.Horizon.Model.TpfTransactionSearchResponse

TPF send history record
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionId** | **string** | Required | Transaction identifier |
| **InstanceId** | **Guid** | Required | Integration instance ID where the transaction was processed |
| **InstanceName** | **string** | Required | Integration instance name |
| **BatchId** | **Guid** | Required | Unique identifier of the batch |
| **RunStartTime** | **DateTimeOffset** | Required | Timestamp when the batch/run started |
| **PublicationStatus** | **string** | Required | Publication status of the transaction (Sent | Skipped | Failed) |
| **InstrumentName** | **string** | Required | Instrument name |
| **InstrumentType** | **string** | Required | Instrument type |
| **TradeDate** | **DateTimeOffset** | Required | Trade date of the transaction |
| **SettlementDate** | **DateTimeOffset?** | Optional | Settlement date of the transaction |
| **SkipReason** | **string** | Optional | Reason the transaction was skipped (if applicable) |
| **FileName** | **string** | Optional | Output file associated with the publication run |
| **Destinations** | **List&lt;string&gt;** | Optional | Destinations to which the transaction was published |
| **PortfolioCode** | **string** | Optional | PortfolioCode showing portfolio code |
| **PortfolioScope** | **string** | Optional | PortfolioScope displaying portfolio scope |
| **FailureReason** | **string** | Optional | FailureReason to show failure reason |
| **InstrumentId** | **string** | Optional | InstrumentId showing instrument id of transaction |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new TpfTransactionSearchResponse(
    transactionId: "...",  // required — Transaction identifier
    instanceId: "...",  // required — Integration instance ID where the transaction was processed
    instanceName: "...",  // required — Integration instance name
    batchId: "...",  // required — Unique identifier of the batch
    runStartTime: DateTimeOffset.Now,  // required — Timestamp when the batch/run started
    publicationStatus: "...",  // required — Publication status of the transaction (Sent | Skipped | Failed)
    instrumentName: "...",  // required — Instrument name
    instrumentType: "...",  // required — Instrument type
    tradeDate: DateTimeOffset.Now,  // required — Trade date of the transaction
    settlementDate: DateTimeOffset.Now,  // optional — Settlement date of the transaction
    skipReason: "...",  // optional — Reason the transaction was skipped (if applicable)
    fileName: "...",  // optional — Output file associated with the publication run
    destinations: ,  // optional — Destinations to which the transaction was published
    portfolioCode: "...",  // optional — PortfolioCode showing portfolio code
    portfolioScope: "...",  // optional — PortfolioScope displaying portfolio scope
    failureReason: "...",  // optional — FailureReason to show failure reason
    instrumentId: "..."  // optional — InstrumentId showing instrument id of transaction
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TpfTransactionSearchResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

