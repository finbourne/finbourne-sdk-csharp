# Finbourne.Sdk.Lusid.Model.EventDateRange

A standard representation of the effective date range for the event, used for display, filtering and windowing use cases.  The start and end values for the eventDateRange are mapped from the particular dates contained within the specific  InstrumentEvent schema.  Note that the start and end values may be identical for some types of events.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Start** | **DateTimeOffset** | Optional | *No description available.* |
| **End** | **DateTimeOffset** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EventDateRange(
    start: DateTimeOffset.Now,  // optional
    end: DateTimeOffset.Now  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EventDateRange>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

