# Finbourne.Sdk.Workflow.Model.EventHandler

Information about an Event Handler
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **VarVersion** | [VersionInfo](VersionInfo.md) | Optional | *No description available.* |
| **DisplayName** | **string** | Required | Human readable name |
| **Description** | **string** | Optional | Human readable description |
| **Status** | **string** | Required | The current status of the event handler |
| **EventMatchingPattern** | [EventMatchingPattern](EventMatchingPattern.md) | Optional | *No description available.* |
| **ScheduleMatchingPattern** | [ScheduleMatchingPattern](ScheduleMatchingPattern.md) | Optional | *No description available.* |
| **RunAsUserId** | [EventHandlerMapping](EventHandlerMapping.md) | Required | *No description available.* |
| **TaskDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **TaskDefinitionAsAt** | **DateTimeOffset?** | Optional | AsAt of the required task definition |
| **TaskActivity** | [TaskActivityResponse](TaskActivityResponse.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new EventHandler(
    id: new ResourceId(...),  // required
    varVersion: new VersionInfo(...),  // optional
    displayName: "...",  // required — Human readable name
    description: "...",  // optional — Human readable description
    status: "...",  // required — The current status of the event handler
    eventMatchingPattern: new EventMatchingPattern(...),  // optional
    scheduleMatchingPattern: new ScheduleMatchingPattern(...),  // optional
    runAsUserId: new EventHandlerMapping(...),  // required
    taskDefinitionId: new ResourceId(...),  // required
    taskDefinitionAsAt: DateTimeOffset.Now,  // optional — AsAt of the required task definition
    taskActivity: new TaskActivityResponse(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EventHandler>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [VersionInfo](VersionInfo.md)
- [EventMatchingPattern](EventMatchingPattern.md)
- [ScheduleMatchingPattern](ScheduleMatchingPattern.md)
- [EventHandlerMapping](EventHandlerMapping.md)
- [ResourceId](ResourceId.md)
- [TaskActivityResponse](TaskActivityResponse.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

