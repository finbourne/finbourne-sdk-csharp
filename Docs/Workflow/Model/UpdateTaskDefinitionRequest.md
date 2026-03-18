# Finbourne.Sdk.Workflow.Model.UpdateTaskDefinitionRequest

Contains required info to update a Task Definition
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | Human readable name |
| **Description** | **string** | Optional | Human readable description |
| **States** | [List&lt;TaskStateDefinition&gt;](TaskStateDefinition.md) | Required | The states this Task Definition operates over |
| **FieldSchema** | [List&lt;TaskFieldDefinition&gt;](TaskFieldDefinition.md) | Optional | Defines the fields associated with this Task |
| **InitialState** | [InitialState](InitialState.md) | Required | *No description available.* |
| **Triggers** | [List&lt;TransitionTriggerDefinition&gt;](TransitionTriggerDefinition.md) | Optional | Triggers |
| **Transitions** | [List&lt;TaskTransitionDefinition&gt;](TaskTransitionDefinition.md) | Optional | Transitions |
| **Actions** | [List&lt;ActionDefinition&gt;](ActionDefinition.md) | Optional | Actions |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new UpdateTaskDefinitionRequest(
    displayName: "...",  // required — Human readable name
    description: "...",  // optional — Human readable description
    states: new List<TaskStateDefinition>(),  // required — The states this Task Definition operates over
    fieldSchema: new List<TaskFieldDefinition>(),  // optional — Defines the fields associated with this Task
    initialState: new InitialState(...),  // required
    triggers: new List<TransitionTriggerDefinition>(),  // optional — Triggers
    transitions: new List<TaskTransitionDefinition>(),  // optional — Transitions
    actions: new List<ActionDefinition>()  // optional — Actions
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateTaskDefinitionRequest>(json);
```

- [TaskStateDefinition](TaskStateDefinition.md) — used in `States`
- [TaskFieldDefinition](TaskFieldDefinition.md) — used in `FieldSchema`
- [InitialState](InitialState.md)
- [TransitionTriggerDefinition](TransitionTriggerDefinition.md) — used in `Triggers`
- [TaskTransitionDefinition](TaskTransitionDefinition.md) — used in `Transitions`
- [ActionDefinition](ActionDefinition.md) — used in `Actions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

