# Finbourne.Sdk.Lusid.Model.VirtualTransactionOverrideRecord

The overrides and suppressions stored against a single instrument event in a single portfolio, together  with their statuses as resolved against the requested portfolio's currently generated virtual  transactions.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentEventId** | **string** | Optional | The identifier of the instrument event this record is stored against. |
| **SourcePortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Overrides** | [Dictionary&lt;string, OverrideEntryResponse&gt;](OverrideEntryResponse.md) | Optional | The overrides stored in this record, keyed by the virtual transaction id being overridden as it appears in the portfolio holding the record. |
| **Suppressions** | [Dictionary&lt;string, SuppressionEntryResponse&gt;](SuppressionEntryResponse.md) | Optional | The suppressions stored in this record, keyed by the virtual transaction id being suppressed as it appears in the portfolio holding the record. |
| **OverrideMatchStatus** | **string** | Optional | Whether every override and suppression entry in this record still matches a virtual transaction the event currently generates. Available values: Matched, Orphaned. |
| **OverrideApplicationStatus** | **string** | Optional | Whether all, some, or none of this record&#39;s override and suppression entries are currently applied. Available values: Full, Partial, Orphaned. |
| **CancelActive** | **bool?** | Optional | True when an active event-level Cancel instruction also exists for this instrument event, taking precedence over the entries in this record. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new VirtualTransactionOverrideRecord(
    instrumentEventId: "...",  // optional — The identifier of the instrument event this record is stored against.
    sourcePortfolioId: new ResourceId(...),  // optional
    overrides: new OverrideEntryResponse(...),  // optional — The overrides stored in this record, keyed by the virtual transaction id being overridden as it appears in the portfolio holding the record.
    suppressions: new SuppressionEntryResponse(...),  // optional — The suppressions stored in this record, keyed by the virtual transaction id being suppressed as it appears in the portfolio holding the record.
    overrideMatchStatus: "...",  // optional — Whether every override and suppression entry in this record still matches a virtual transaction the event currently generates. Available values: Matched, Orphaned.
    overrideApplicationStatus: "...",  // optional — Whether all, some, or none of this record&#39;s override and suppression entries are currently applied. Available values: Full, Partial, Orphaned.
    cancelActive: true,  // optional — True when an active event-level Cancel instruction also exists for this instrument event, taking precedence over the entries in this record.
    varVersion: new ModelVersion(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VirtualTransactionOverrideRecord>(json);
```

- [ResourceId](ResourceId.md)
- [OverrideEntryResponse](OverrideEntryResponse.md) — used in `Overrides`
- [SuppressionEntryResponse](SuppressionEntryResponse.md) — used in `Suppressions`
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

