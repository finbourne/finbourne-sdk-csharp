# Finbourne.Sdk.Horizon.Model.TpfTransactionSearchResponse

TPF send history record
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionId** | **string** | Required | Transaction identifier |
| **InstanceId** | **Guid** | Required | Integration instance ID where the transaction was processed |
| **InstanceName** | **string** | Required | Integration instance name |
| **BatchId** | **Guid** | Required | Unique identifier of the batch |
| **RunId** | **Guid** | Required | The run that processed the transaction for this instance, as shown in run monitoring |
| **RunStartTime** | **DateTimeOffset** | Required | Timestamp when the batch/run started |
| **PublicationStatus** | **string** | Required | Outcome of the transaction&#39;s build (Sent | Skipped | Failed) |
| **Outcome** | **string** | Required | The same value as PublicationStatus under the name the screens use; PublicationStatus stays for existing clients. |
| **EventType** | **string** | Optional | The TPF event type that triggered this publication (New, Amended, Cancelled, NothingToDo, InstrumentMatured, InstrumentPartialClosure, InstrumentFullClosure, InstrumentInterestPayment, LastSentPropertyUpdated). Null for rows persisted before it was recorded, for transactions skipped as excluded, and for rows written before the build computed it (for example a transaction not found in LUSID). Never Queued: the search returns built rows only. Distinct from PublicationStatus, which says what happened to the row. |
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
| **FailureStage** | **string** | Optional | Stage at which a failed transaction failed: Build or Delivery |
| **SentAt** | **DateTimeOffset?** | Optional | When the transaction was sent, which is when its file reached a destination. Empty for Skipped and Failed rows |
| **InstrumentId** | **string** | Optional | InstrumentId showing instrument id of transaction |
| **InstrumentScope** | **string** | Optional | The scope the build resolved the instrument in; null for rows built before it was recorded |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new TpfTransactionSearchResponse(
    transactionId: "...",  // required — Transaction identifier
    instanceId: "...",  // required — Integration instance ID where the transaction was processed
    instanceName: "...",  // required — Integration instance name
    batchId: "...",  // required — Unique identifier of the batch
    runId: "...",  // required — The run that processed the transaction for this instance, as shown in run monitoring
    runStartTime: DateTimeOffset.Now,  // required — Timestamp when the batch/run started
    publicationStatus: "...",  // required — Outcome of the transaction&#39;s build (Sent | Skipped | Failed)
    outcome: "...",  // required — The same value as PublicationStatus under the name the screens use; PublicationStatus stays for existing clients.
    eventType: "...",  // optional — The TPF event type that triggered this publication (New, Amended, Cancelled, NothingToDo, InstrumentMatured, InstrumentPartialClosure, InstrumentFullClosure, InstrumentInterestPayment, LastSentPropertyUpdated). Null for rows persisted before it was recorded, for transactions skipped as excluded, and for rows written before the build computed it (for example a transaction not found in LUSID). Never Queued: the search returns built rows only. Distinct from PublicationStatus, which says what happened to the row.
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
    failureStage: "...",  // optional — Stage at which a failed transaction failed: Build or Delivery
    sentAt: DateTimeOffset.Now,  // optional — When the transaction was sent, which is when its file reached a destination. Empty for Skipped and Failed rows
    instrumentId: "...",  // optional — InstrumentId showing instrument id of transaction
    instrumentScope: "..."  // optional — The scope the build resolved the instrument in; null for rows built before it was recorded
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

