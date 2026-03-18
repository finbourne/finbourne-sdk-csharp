# Finbourne.Sdk.Horizon.Model.UpdateInstanceRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | *No description available.* |
| **IntegrationType** | **string** | Required | *No description available.* |
| **Name** | **string** | Required | *No description available.* |
| **Description** | **string** | Required | *No description available.* |
| **Enabled** | **bool** | Required | *No description available.* |
| **Triggers** | [List&lt;Trigger&gt;](Trigger.md) | Required | *No description available.* |
| **Details** | **Object** | Required | *No description available.* |
| **PostProcessTasks** | [List&lt;PostProcessTask&gt;](PostProcessTask.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new UpdateInstanceRequest(
    id: "...",  // required
    integrationType: "...",  // required
    name: "...",  // required
    description: "...",  // required
    enabled: true,  // required
    triggers: new List<Trigger>(),  // required
    details: ,  // required
    postProcessTasks: new List<PostProcessTask>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateInstanceRequest>(json);
```

- [Trigger](Trigger.md)
- [PostProcessTask](PostProcessTask.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

