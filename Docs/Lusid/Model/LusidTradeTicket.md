# Finbourne.Sdk.Lusid.Model.LusidTradeTicket

A LUSID Trade Ticket comprising an instrument, a transaction, and a counterparty.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionId** | **string** | Required | Transaction ID. Must be unique. |
| **TransactionType** | **string** | Required | Type of transaction for processing. Referenced by Transaction Configuration. |
| **Source** | **string** | Optional | Transaction Source. Referenced by Transaction Configuration. |
| **TransactionDate** | **string** | Required | Transaction Date. Date at which transaction is known. |
| **SettlementDate** | **string** | Required | Transaction settlement. Date at which transaction is finalised and realised into the system. |
| **TotalConsideration** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **Units** | **decimal** | Required | Number of units in the transaction. For an OTC this is somewhat interchangeable with the quantity booked in the  instrument. As M x N or N x M are equivalent it is advised a client chooses one approach and sticks to it.  Arguably either the unit or holding is best unitised. |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | Identifiers for the instrument. |
| **InstrumentScope** | **string** | Optional | Scope of instrument |
| **InstrumentName** | **string** | Optional | Name of instrument |
| **InstrumentDefinition** | [LusidInstrument](LusidInstrument.md) | Optional | *No description available.* |
| **CounterpartyAgreementId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Counterparty** | **string** | Optional | Counterparty |
| **InstrumentProperties** | [List&lt;Property&gt;](Property.md) | Optional | Set of instrument properties (as defined by client/user). |
| **TransactionProperties** | [List&lt;Property&gt;](Property.md) | Optional | Set of transaction properties (as defined by client/user). |
| **TradeTicketType** | **string** | Required | The available values are: LusidTradeTicket, ExternalTradeTicket |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new LusidTradeTicket(
    transactionId: "...",  // required — Transaction ID. Must be unique.
    transactionType: "...",  // required — Type of transaction for processing. Referenced by Transaction Configuration.
    source: "...",  // optional — Transaction Source. Referenced by Transaction Configuration.
    transactionDate: "...",  // required — Transaction Date. Date at which transaction is known.
    settlementDate: "...",  // required — Transaction settlement. Date at which transaction is finalised and realised into the system.
    totalConsideration: new CurrencyAndAmount(...),  // required
    units: 0.0d,  // required — Number of units in the transaction. For an OTC this is somewhat interchangeable with the quantity booked in the  instrument. As M x N or N x M are equivalent it is advised a client chooses one approach and sticks to it.  Arguably either the unit or holding is best unitised.
    instrumentIdentifiers: ,  // required — Identifiers for the instrument.
    instrumentScope: "...",  // optional — Scope of instrument
    instrumentName: "...",  // optional — Name of instrument
    instrumentDefinition: new LusidInstrument(...),  // optional
    counterpartyAgreementId: new ResourceId(...),  // optional
    counterparty: "...",  // optional — Counterparty
    instrumentProperties: new List<Property>(),  // optional — Set of instrument properties (as defined by client/user).
    transactionProperties: new List<Property>(),  // optional — Set of transaction properties (as defined by client/user).
    tradeTicketType: "..."  // required — The available values are: LusidTradeTicket, ExternalTradeTicket
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LusidTradeTicket>(json);
```

- [CurrencyAndAmount](CurrencyAndAmount.md)
- [LusidInstrument](LusidInstrument.md)
- [ResourceId](ResourceId.md)
- [Property](Property.md) — used in `InstrumentProperties`
- [Property](Property.md) — used in `TransactionProperties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

