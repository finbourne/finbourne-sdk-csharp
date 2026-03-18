# Finbourne.Sdk.Workflow.Model.ActionDefinitionResponse

Defines the Actions for a Task in a read-only form
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Optional | The Name of this Action |
| **RunAsUserId** | **string** | Optional | The ID of the user that this action will be performed by. If not specified, the actions will be performed by the \&quot;current user\&quot;. |
| **ActionDetails** | [ActionDetailsResponse](ActionDetailsResponse.md) | Optional | *No description available.* |
| **DisplayName** | **string** | Optional | Schema for the Action |
| **Description** | **string** | Optional | Schema for the Action |
| **Category** | **string** | Optional | Schema for the Action |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ActionDefinitionResponse(
    name: "...",  // optional — The Name of this Action
    runAsUserId: "...",  // optional — The ID of the user that this action will be performed by. If not specified, the actions will be performed by the \&quot;current user\&quot;.
    actionDetails: new ActionDetailsResponse(...),  // optional
    displayName: "...",  // optional — Schema for the Action
    description: "...",  // optional — Schema for the Action
    category: "..."  // optional — Schema for the Action
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ActionDefinitionResponse>(json);
```

- [ActionDetailsResponse](ActionDetailsResponse.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

