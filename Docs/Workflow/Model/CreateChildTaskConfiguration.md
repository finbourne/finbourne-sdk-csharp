# Finbourne.Sdk.Workflow.Model.CreateChildTaskConfiguration

Create Child Task Configuration
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TaskDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **TaskDefinitionAsAt** | **DateTimeOffset?** | Optional | TaskDefinition AsAt timestamp |
| **InitialTrigger** | **string** | Optional | The Initial Trigger for automatic start |
| **ChildTaskFields** | [Dictionary&lt;string, FieldMapping&gt;](FieldMapping.md) | Optional | Field Mappings |
| **MapStackingKeyFrom** | **string** | Optional | If present, the value of this field on the parent task will be the Stacking Key on any created child tasks |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new CreateChildTaskConfiguration(
    taskDefinitionId: new ResourceId(...),  // required
    taskDefinitionAsAt: DateTimeOffset.Now,  // optional — TaskDefinition AsAt timestamp
    initialTrigger: "...",  // optional — The Initial Trigger for automatic start
    childTaskFields: new FieldMapping(...),  // optional — Field Mappings
    mapStackingKeyFrom: "..."  // optional — If present, the value of this field on the parent task will be the Stacking Key on any created child tasks
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateChildTaskConfiguration>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [FieldMapping](FieldMapping.md) — used in `ChildTaskFields`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

