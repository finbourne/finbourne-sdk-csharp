# Finbourne.Sdk.Lusid.Model.LifeCycleEventLineage

The lineage of the event value
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EventType** | **string** | Optional | The type of the event |
| **InstrumentType** | **string** | Optional | The instrument type of the instrument for the event. |
| **InstrumentId** | **string** | Optional | The LUID of the instrument for the event. |
| **LegId** | **string** | Optional | Leg id for the event. |
| **SourceTransactionId** | **string** | Optional | The source transaction of the instrument for the event. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new LifeCycleEventLineage(
    eventType: "...",  // optional — The type of the event
    instrumentType: "...",  // optional — The instrument type of the instrument for the event.
    instrumentId: "...",  // optional — The LUID of the instrument for the event.
    legId: "...",  // optional — Leg id for the event.
    sourceTransactionId: "..."  // optional — The source transaction of the instrument for the event.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LifeCycleEventLineage>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

