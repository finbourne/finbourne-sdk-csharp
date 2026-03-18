# Finbourne.Sdk.Workflow.Model.WorkflowResponse

A Workflow
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **VarVersion** | [VersionInfo](VersionInfo.md) | Optional | *No description available.* |
| **DisplayName** | **string** | Required | Human readable name |
| **Description** | **string** | Optional | Human readable description |
| **RootTaskDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **WorkflowStructure** | [WorkflowStructure](WorkflowStructure.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new WorkflowResponse(
    id: new ResourceId(...),  // required
    varVersion: new VersionInfo(...),  // optional
    displayName: "...",  // required — Human readable name
    description: "...",  // optional — Human readable description
    rootTaskDefinitionId: new ResourceId(...),  // required
    workflowStructure: new WorkflowStructure(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkflowResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [VersionInfo](VersionInfo.md)
- [ResourceId](ResourceId.md)
- [WorkflowStructure](WorkflowStructure.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

