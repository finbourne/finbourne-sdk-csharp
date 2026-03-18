# Finbourne.Sdk.Workflow.Model.ActionDefinition

Defines the Actions for a Task
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The Name of this Action |
| **RunAsUserId** | **string** | Optional | The ID of the user that this action will be performed by. If not specified, the actions will be performed by the \&quot;current user\&quot;. |
| **ActionDetails** | [ActionDetails](ActionDetails.md) | Required | *No description available.* |
| **DisplayName** | **string** | Optional | The display name of this Action |
| **Description** | **string** | Optional | The description of this Action |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ActionDefinition(
    name: "...",  // required — The Name of this Action
    runAsUserId: "...",  // optional — The ID of the user that this action will be performed by. If not specified, the actions will be performed by the \&quot;current user\&quot;.
    actionDetails: new ActionDetails(...),  // required
    displayName: "...",  // optional — The display name of this Action
    description: "..."  // optional — The description of this Action
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ActionDefinition>(json);
```

- [ActionDetails](ActionDetails.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

