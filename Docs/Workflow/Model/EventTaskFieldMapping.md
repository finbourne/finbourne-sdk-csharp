# Finbourne.Sdk.Workflow.Model.EventTaskFieldMapping

How an Event Launcher fills one field of the root task from the event that arrived
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MapFrom** | **string** | Required | The path into the event the value is taken from, for example header.timestamp |
| **DateTimeAdjustment** | [DateTimeAdjustment](DateTimeAdjustment.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new EventTaskFieldMapping(
    mapFrom: "...",  // required — The path into the event the value is taken from, for example header.timestamp
    dateTimeAdjustment: new DateTimeAdjustment(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EventTaskFieldMapping>(json);
```

- [DateTimeAdjustment](DateTimeAdjustment.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

