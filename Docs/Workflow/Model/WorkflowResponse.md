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
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The properties of the Workflow, keyed by property key. |


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
    workflowStructure: new WorkflowStructure(...),  // optional
    properties: new PerpetualProperty(...)  // optional — The properties of the Workflow, keyed by property key.
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
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

