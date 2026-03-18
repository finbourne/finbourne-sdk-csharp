# Finbourne.Sdk.Workflow.Model.ActionLogOrigin

The Action Log Origin contains information about how the Action was created
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TaskId** | **Guid?** | Optional | The Id of the Task that created this Action |
| **RequestId** | **string** | Required | The request Id of the request that caused this Action to be triggered. This could be the original request that caused a sequence of Actions that resulted in this Action |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ActionLogOrigin(
    taskId: "...",  // optional — The Id of the Task that created this Action
    requestId: "..."  // required — The request Id of the request that caused this Action to be triggered. This could be the original request that caused a sequence of Actions that resulted in this Action
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ActionLogOrigin>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

