# Finbourne.Sdk.Horizon.Model.WorkflowResultFieldsTaskResponse

One of the instance's enabled RunWorkflow post-process tasks.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | *No description available.* |
| **TriggerOn** | **string** | Required | When this task fires: OnSuccess, OnFailure or Always. |
| **ResultFields** | **List&lt;string&gt;** | Required | Names of the fields this particular task declares. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new WorkflowResultFieldsTaskResponse(
    name: "...",  // required
    triggerOn: "...",  // required — When this task fires: OnSuccess, OnFailure or Always.
    resultFields:   // required — Names of the fields this particular task declares.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkflowResultFieldsTaskResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

