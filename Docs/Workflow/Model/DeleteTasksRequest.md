# Finbourne.Sdk.Workflow.Model.DeleteTasksRequest

Contains required info to delete Tasks
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TaskIds** | **List&lt;string&gt;** | Optional | The Ids of the Tasks to delete |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new DeleteTasksRequest(
    taskIds:   // optional — The Ids of the Tasks to delete
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DeleteTasksRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

