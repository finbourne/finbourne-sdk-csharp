# Finbourne.Sdk.Workflow.Model.TransitionTriggerDefinition

State changes happen in response to Triggers
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The key/Name of this Trigger |
| **Trigger** | [TriggerSchema](TriggerSchema.md) | Required | *No description available.* |
| **DisplayName** | **string** | Optional | Display name for trigger |
| **Description** | **string** | Optional | Description of trigger |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new TransitionTriggerDefinition(
    name: "...",  // required — The key/Name of this Trigger
    trigger: new TriggerSchema(...),  // required
    displayName: "...",  // optional — Display name for trigger
    description: "..."  // optional — Description of trigger
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransitionTriggerDefinition>(json);
```

- [TriggerSchema](TriggerSchema.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

