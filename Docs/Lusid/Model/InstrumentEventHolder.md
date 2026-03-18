# Finbourne.Sdk.Lusid.Model.InstrumentEventHolder

An instrument event equipped with additional metadata.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentEventId** | **string** | Required | The unique identifier of this corporate action. |
| **CorporateActionSourceId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | The set of identifiers which determine the instrument this event relates to. |
| **LusidInstrumentId** | **string** | Required | The LUID for the instrument. |
| **InstrumentScope** | **string** | Required | The scope of the instrument. |
| **Description** | **string** | Required | The description of the instrument event. |
| **EventDateRange** | [EventDateRange](EventDateRange.md) | Required | *No description available.* |
| **Completeness** | **string** | Optional | Is the event Economically Complete, or is it missing some DataDependent fields (Incomplete). *(read-only)* |
| **InstrumentEvent** | [InstrumentEvent](InstrumentEvent.md) | Required | *No description available.* |
| **Properties** | [List&lt;PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The properties attached to this instrument event. |
| **SequenceNumber** | **int** | Optional | The order of the instrument event relative others on the same date (0 being processed first). Must be non negative. |
| **ParticipationType** | **string** | Optional | Is participation in this event Mandatory, MandatoryWithChoices, or Voluntary. Default: `"Mandatory"` |
| **AsAt** | **DateTimeOffset?** | Optional | The AsAt time of the instrument event, if available. This is a readonly field and should not be provided on upsert. *(read-only)* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentEventHolder(
    instrumentEventId: "...",  // required — The unique identifier of this corporate action.
    corporateActionSourceId: new ResourceId(...),  // optional
    instrumentIdentifiers: ,  // required — The set of identifiers which determine the instrument this event relates to.
    lusidInstrumentId: "...",  // required — The LUID for the instrument.
    instrumentScope: "...",  // required — The scope of the instrument.
    description: "...",  // required — The description of the instrument event.
    eventDateRange: new EventDateRange(...),  // required
    completeness: "...",  // optional — Is the event Economically Complete, or is it missing some DataDependent fields (Incomplete).
    instrumentEvent: new InstrumentEvent(...),  // required
    properties: new List<PerpetualProperty>(),  // optional — The properties attached to this instrument event.
    sequenceNumber: 0,  // optional — The order of the instrument event relative others on the same date (0 being processed first). Must be non negative.
    participationType: "...",  // optional — Is participation in this event Mandatory, MandatoryWithChoices, or Voluntary.
    asAt: DateTimeOffset.Now  // optional — The AsAt time of the instrument event, if available. This is a readonly field and should not be provided on upsert.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentEventHolder>(json);
```

- [ResourceId](ResourceId.md)
- [EventDateRange](EventDateRange.md)
- [InstrumentEvent](InstrumentEvent.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

