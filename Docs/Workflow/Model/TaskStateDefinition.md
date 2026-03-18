# Finbourne.Sdk.Workflow.Model.TaskStateDefinition

A Task Definition/Task has a given set of States
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The Name of this State |
| **DisplayName** | **string** | Optional | The display name of this State |
| **Description** | **string** | Optional | The description of this State |
| **Category** | **string** | Optional | The category of this State |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new TaskStateDefinition(
    name: "...",  // required — The Name of this State
    displayName: "...",  // optional — The display name of this State
    description: "...",  // optional — The description of this State
    category: "..."  // optional — The category of this State
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaskStateDefinition>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

