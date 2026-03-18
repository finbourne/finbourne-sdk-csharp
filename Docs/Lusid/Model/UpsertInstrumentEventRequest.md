# Finbourne.Sdk.Lusid.Model.UpsertInstrumentEventRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentEventId** | **string** | Required | Free string that uniquely identifies the event within the corporate action source |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | The set of identifiers which determine the instrument this event relates to. |
| **Description** | **string** | Optional | The description of the instrument event. |
| **InstrumentEvent** | [InstrumentEvent](InstrumentEvent.md) | Required | *No description available.* |
| **Properties** | [List&lt;PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The properties attached to this instrument event. |
| **SequenceNumber** | **int** | Optional | The order of the instrument event relative others on the same date (0 being processed first). Must be non negative. |
| **ParticipationType** | **string** | Optional | Is participation in this event Mandatory, MandatoryWithChoices, or Voluntary. Default: `"Mandatory"` |
| **EventDateStamps** | [Dictionary&lt;string, YearMonthDay&gt;](YearMonthDay.md) | Optional | The date stamps corresponding to the relevant date-time fields for the instrument event. The key for each provided date stamp must match the field name of a valid datetime field from the InstrumentEvent DTO. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertInstrumentEventRequest(
    instrumentEventId: "...",  // required — Free string that uniquely identifies the event within the corporate action source
    instrumentIdentifiers: ,  // required — The set of identifiers which determine the instrument this event relates to.
    description: "...",  // optional — The description of the instrument event.
    instrumentEvent: new InstrumentEvent(...),  // required
    properties: new List<PerpetualProperty>(),  // optional — The properties attached to this instrument event.
    sequenceNumber: 0,  // optional — The order of the instrument event relative others on the same date (0 being processed first). Must be non negative.
    participationType: "...",  // optional — Is participation in this event Mandatory, MandatoryWithChoices, or Voluntary.
    eventDateStamps: new YearMonthDay(...)  // optional — The date stamps corresponding to the relevant date-time fields for the instrument event. The key for each provided date stamp must match the field name of a valid datetime field from the InstrumentEvent DTO.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertInstrumentEventRequest>(json);
```

- [InstrumentEvent](InstrumentEvent.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [YearMonthDay](YearMonthDay.md) — used in `EventDateStamps`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

