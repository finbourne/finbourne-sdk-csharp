# Finbourne.Sdk.Workflow.Model.UpdateWorkflowRequest

Contains required info to update an existing Workflow
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | Human readable name |
| **Description** | **string** | Optional | Human readable description |
| **RootTaskDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The properties to set on the Workflow, keyed by property key. Optional. A null property value deletes the property. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new UpdateWorkflowRequest(
    displayName: "...",  // required — Human readable name
    description: "...",  // optional — Human readable description
    rootTaskDefinitionId: new ResourceId(...),  // required
    properties: new PerpetualProperty(...)  // optional — The properties to set on the Workflow, keyed by property key. Optional. A null property value deletes the property.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateWorkflowRequest>(json);
```

- [ResourceId](ResourceId.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

