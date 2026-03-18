# Finbourne.Sdk.Workflow.Model.CreateEventHandlerRequest

Contains information for creating an Event Handler
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | Human readable name |
| **Description** | **string** | Optional | Human readable description |
| **Status** | **string** | Required | The current status of the event handler |
| **EventMatchingPattern** | [EventMatchingPattern](EventMatchingPattern.md) | Optional | *No description available.* |
| **ScheduleMatchingPattern** | [ScheduleMatchingPattern](ScheduleMatchingPattern.md) | Optional | *No description available.* |
| **RunAsUserId** | [EventHandlerMapping](EventHandlerMapping.md) | Required | *No description available.* |
| **TaskDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **TaskDefinitionAsAt** | **DateTimeOffset?** | Optional | AsAt of the required task definition |
| **TaskActivity** | [TaskActivity](TaskActivity.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new CreateEventHandlerRequest(
    id: new ResourceId(...),  // required
    displayName: "...",  // required — Human readable name
    description: "...",  // optional — Human readable description
    status: "...",  // required — The current status of the event handler
    eventMatchingPattern: new EventMatchingPattern(...),  // optional
    scheduleMatchingPattern: new ScheduleMatchingPattern(...),  // optional
    runAsUserId: new EventHandlerMapping(...),  // required
    taskDefinitionId: new ResourceId(...),  // required
    taskDefinitionAsAt: DateTimeOffset.Now,  // optional — AsAt of the required task definition
    taskActivity: new TaskActivity(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateEventHandlerRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [EventMatchingPattern](EventMatchingPattern.md)
- [ScheduleMatchingPattern](ScheduleMatchingPattern.md)
- [EventHandlerMapping](EventHandlerMapping.md)
- [ResourceId](ResourceId.md)
- [TaskActivity](TaskActivity.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

