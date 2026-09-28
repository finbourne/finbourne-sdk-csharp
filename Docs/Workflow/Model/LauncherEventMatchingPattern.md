# Finbourne.Sdk.Workflow.Model.LauncherEventMatchingPattern

Which events make an Event Launcher start a run of its Workflow
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EventType** | **string** | Required | The type of event to listen for. The list of available event types can be discovered by calling the ListEventTypes API endpoint in the Notifications service. Note that event types published by the Workflow service itself are not supported as Launcher triggers, and giving one will be rejected. |
| **Filter** | **string** | Optional | A filter on the event. See https://support.lusid.com/filtering-results-from-lusid for more information. An empty filter matches every event of the type |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new LauncherEventMatchingPattern(
    eventType: "...",  // required — The type of event to listen for. The list of available event types can be discovered by calling the ListEventTypes API endpoint in the Notifications service. Note that event types published by the Workflow service itself are not supported as Launcher triggers, and giving one will be rejected.
    filter: "..."  // optional — A filter on the event. See https://support.lusid.com/filtering-results-from-lusid for more information. An empty filter matches every event of the type
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LauncherEventMatchingPattern>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

