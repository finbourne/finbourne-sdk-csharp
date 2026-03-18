# Finbourne.Sdk.Workflow.Model.BatchUpdateTasksResponse

Defines a representation of tasks that have been updated
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [List&lt;Task&gt;](Task.md) | Optional | Successful tasks brought back from the BatchUpdate call *(read-only)* |
| **Failed** | [List&lt;ErrorDetail&gt;](ErrorDetail.md) | Optional | Individual failures for each task returned from the BatchUpdate call *(read-only)* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new BatchUpdateTasksResponse(
    values: new List<Task>(),  // optional — Successful tasks brought back from the BatchUpdate call
    failed: new List<ErrorDetail>(),  // optional — Individual failures for each task returned from the BatchUpdate call
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchUpdateTasksResponse>(json);
```


## Related Models

- [Task](Task.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

