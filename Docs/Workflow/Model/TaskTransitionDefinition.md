# Finbourne.Sdk.Workflow.Model.TaskTransitionDefinition

Defines a State change
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FromState** | **string** | Required | The State this Transition if coming From |
| **ToState** | **string** | Required | The State this Transition is going To |
| **Trigger** | **string** | Required | The Trigger for this Transition |
| **Guard** | **string** | Optional | The Guard for this Transition, if any |
| **Action** | **string** | Optional | The Action to invoke on successful Transition |
| **DisplayName** | **string** | Optional | Display name for transition |
| **Description** | **string** | Optional | Description for transition |
| **GuardDescription** | **string** | Optional | Guard description for transition |
| **GuardConditionNotMetMessage** | **string** | Optional | Message when guard has not been met |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new TaskTransitionDefinition(
    fromState: "...",  // required — The State this Transition if coming From
    toState: "...",  // required — The State this Transition is going To
    trigger: "...",  // required — The Trigger for this Transition
    guard: "...",  // optional — The Guard for this Transition, if any
    action: "...",  // optional — The Action to invoke on successful Transition
    displayName: "...",  // optional — Display name for transition
    description: "...",  // optional — Description for transition
    guardDescription: "...",  // optional — Guard description for transition
    guardConditionNotMetMessage: "..."  // optional — Message when guard has not been met
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaskTransitionDefinition>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

