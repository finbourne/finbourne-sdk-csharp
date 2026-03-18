# Finbourne.Sdk.Workflow.Model.TaskInstanceField

Defines a Field on a Task
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name of this Field |
| **Value** | **Object** | Optional | The value of this Field |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new TaskInstanceField(
    name: "...",  // required — The name of this Field
    value:   // optional — The value of this Field
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaskInstanceField>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

