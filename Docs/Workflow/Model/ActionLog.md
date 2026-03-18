# Finbourne.Sdk.Workflow.Model.ActionLog

An Action Log contains the processing history of an Action
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **Guid** | Required | Unique identifier of the Action |
| **Origin** | [ActionLogOrigin](ActionLogOrigin.md) | Required | *No description available.* |
| **ActionType** | **string** | Required | The type of the Action |
| **RunAsUserId** | **string** | Optional | The ID of the user that the Action was performed by. If not specified, the actions were performed by the \&quot;current user\&quot;. |
| **LoggedItems** | [List&lt;ActionLogItem&gt;](ActionLogItem.md) | Required | The logged items for this Action |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ActionLog(
    id: "...",  // required — Unique identifier of the Action
    origin: new ActionLogOrigin(...),  // required
    actionType: "...",  // required — The type of the Action
    runAsUserId: "...",  // optional — The ID of the user that the Action was performed by. If not specified, the actions were performed by the \&quot;current user\&quot;.
    loggedItems: new List<ActionLogItem>()  // required — The logged items for this Action
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ActionLog>(json);
```

- [ActionLogOrigin](ActionLogOrigin.md)
- [ActionLogItem](ActionLogItem.md) — used in `LoggedItems`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

