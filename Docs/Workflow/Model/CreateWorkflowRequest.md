# Finbourne.Sdk.Workflow.Model.CreateWorkflowRequest

Contains required info to create a new Workflow
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | Human readable name |
| **Description** | **string** | Optional | Human readable description |
| **RootTaskDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new CreateWorkflowRequest(
    id: new ResourceId(...),  // required
    displayName: "...",  // required — Human readable name
    description: "...",  // optional — Human readable description
    rootTaskDefinitionId: new ResourceId(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateWorkflowRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

