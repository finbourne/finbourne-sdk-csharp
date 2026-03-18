# Finbourne.Sdk.Lusid.Model.ApplicableInstrumentEvent

Represents applicable instrument event.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **HoldingId** | **long** | Required | *No description available.* |
| **LusidInstrumentId** | **string** | Required | *No description available.* |
| **InstrumentScope** | **string** | Required | *No description available.* |
| **InstrumentType** | **string** | Required | *No description available.* |
| **InstrumentEventType** | **string** | Required | *No description available.* |
| **InstrumentEventId** | **string** | Required | *No description available.* |
| **GeneratedEvent** | [InstrumentEventHolder](InstrumentEventHolder.md) | Optional | *No description available.* |
| **GeneratedEventDiagnostics** | [GeneratedEventDiagnostics](GeneratedEventDiagnostics.md) | Optional | *No description available.* |
| **LoadedEvent** | [InstrumentEventHolder](InstrumentEventHolder.md) | Optional | *No description available.* |
| **AppliedInstrumentEventInstructionId** | **string** | Optional | *No description available.* |
| **Transactions** | [List&lt;Transaction&gt;](Transaction.md) | Optional | *No description available.* |
| **TransactionDiagnostics** | [TransactionDiagnostics](TransactionDiagnostics.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ApplicableInstrumentEvent(
    portfolioId: new ResourceId(...),  // required
    holdingId: 0L,  // required
    lusidInstrumentId: "...",  // required
    instrumentScope: "...",  // required
    instrumentType: "...",  // required
    instrumentEventType: "...",  // required
    instrumentEventId: "...",  // required
    generatedEvent: new InstrumentEventHolder(...),  // optional
    generatedEventDiagnostics: new GeneratedEventDiagnostics(...),  // optional
    loadedEvent: new InstrumentEventHolder(...),  // optional
    appliedInstrumentEventInstructionId: "...",  // optional
    transactions: new List<Transaction>(),  // optional
    transactionDiagnostics: new TransactionDiagnostics(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ApplicableInstrumentEvent>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [InstrumentEventHolder](InstrumentEventHolder.md)
- [GeneratedEventDiagnostics](GeneratedEventDiagnostics.md)
- [InstrumentEventHolder](InstrumentEventHolder.md)
- [Transaction](Transaction.md)
- [TransactionDiagnostics](TransactionDiagnostics.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

