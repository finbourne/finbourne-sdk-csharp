# Finbourne.Sdk.Workflow.Model.EventLauncherDetails

A Launcher that starts a run of its Workflow when a matching platform event arrives, and can fill fields and correlation IDs of the root task from that event
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LauncherType** | **string** | Required | *No description available.* |
| **EventMatchingPattern** | [LauncherEventMatchingPattern](LauncherEventMatchingPattern.md) | Required | *No description available.* |
| **MapTaskFields** | [Dictionary&lt;string, EventTaskFieldMapping&gt;](EventTaskFieldMapping.md) | Optional | Fields of the root task filled from the event, keyed by the field name on the root task definition |
| **MapCorrelationIds** | [List&lt;CorrelationIdMapping&gt;](CorrelationIdMapping.md) | Optional | Correlation IDs of the root task filled from the event |
| **RunAsUserId** | [LauncherMapping](LauncherMapping.md) | Required | *No description available.* |
| **SetTaskFields** | **Dictionary&lt;string, Object&gt;** | Optional | Fields of the root task set to a fixed value, keyed by the field name on the root task definition |
| **SetCorrelationIds** | **List&lt;string&gt;** | Optional | Correlation IDs put on the root task as given |
| **InitialTrigger** | **string** | Optional | The trigger given to the root task once it is made and all of its fields are filled. When it is left out the root task is left in its initial state |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new EventLauncherDetails(
    launcherType: "...",  // required
    eventMatchingPattern: new LauncherEventMatchingPattern(...),  // required
    mapTaskFields: new EventTaskFieldMapping(...),  // optional — Fields of the root task filled from the event, keyed by the field name on the root task definition
    mapCorrelationIds: new List<CorrelationIdMapping>(),  // optional — Correlation IDs of the root task filled from the event
    runAsUserId: new LauncherMapping(...),  // required
    setTaskFields: ,  // optional — Fields of the root task set to a fixed value, keyed by the field name on the root task definition
    setCorrelationIds: ,  // optional — Correlation IDs put on the root task as given
    initialTrigger: "..."  // optional — The trigger given to the root task once it is made and all of its fields are filled. When it is left out the root task is left in its initial state
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EventLauncherDetails>(json);
```

- [LauncherEventMatchingPattern](LauncherEventMatchingPattern.md)
- [EventTaskFieldMapping](EventTaskFieldMapping.md) — used in `MapTaskFields`
- [CorrelationIdMapping](CorrelationIdMapping.md) — used in `MapCorrelationIds`
- [LauncherMapping](LauncherMapping.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

