# Finbourne.Sdk.Workflow.Model.TaskDefinition

Task Definition
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **VarVersion** | [VersionInfo](VersionInfo.md) | Optional | *No description available.* |
| **DisplayName** | **string** | Required | Human readable name |
| **Description** | **string** | Optional | Human readable description |
| **States** | [List&lt;TaskStateDefinition&gt;](TaskStateDefinition.md) | Required | The states this Task Definition operates over |
| **FieldSchema** | [List&lt;TaskFieldDefinition&gt;](TaskFieldDefinition.md) | Optional | The Fields that this Task Definition operates on |
| **InitialState** | [InitialState](InitialState.md) | Required | *No description available.* |
| **Triggers** | [List&lt;TransitionTriggerDefinition&gt;](TransitionTriggerDefinition.md) | Optional | The Triggers for State transition |
| **Actions** | [List&lt;ActionDefinitionResponse&gt;](ActionDefinitionResponse.md) | Optional | The Actions of this Task - executed after a Transition completion |
| **Transitions** | [List&lt;TaskTransitionDefinition&gt;](TaskTransitionDefinition.md) | Optional | The Transitions between States |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new TaskDefinition(
    id: new ResourceId(...),  // required
    varVersion: new VersionInfo(...),  // optional
    displayName: "...",  // required — Human readable name
    description: "...",  // optional — Human readable description
    states: new List<TaskStateDefinition>(),  // required — The states this Task Definition operates over
    fieldSchema: new List<TaskFieldDefinition>(),  // optional — The Fields that this Task Definition operates on
    initialState: new InitialState(...),  // required
    triggers: new List<TransitionTriggerDefinition>(),  // optional — The Triggers for State transition
    actions: new List<ActionDefinitionResponse>(),  // optional — The Actions of this Task - executed after a Transition completion
    transitions: new List<TaskTransitionDefinition>()  // optional — The Transitions between States
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaskDefinition>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [VersionInfo](VersionInfo.md)
- [TaskStateDefinition](TaskStateDefinition.md) — used in `States`
- [TaskFieldDefinition](TaskFieldDefinition.md) — used in `FieldSchema`
- [InitialState](InitialState.md)
- [TransitionTriggerDefinition](TransitionTriggerDefinition.md) — used in `Triggers`
- [ActionDefinitionResponse](ActionDefinitionResponse.md) — used in `Actions`
- [TaskTransitionDefinition](TaskTransitionDefinition.md) — used in `Transitions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

