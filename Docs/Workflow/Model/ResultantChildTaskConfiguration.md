# Finbourne.Sdk.Workflow.Model.ResultantChildTaskConfiguration

Child Task Configuration
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ResultMatchingPattern** | [ResultMatchingPattern](ResultMatchingPattern.md) | Optional | *No description available.* |
| **TaskDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **TaskDefinitionAsAt** | **DateTimeOffset?** | Optional | TaskDefinition AsAt timestamp |
| **InitialTrigger** | **string** | Optional | The Initial Trigger for automatic start |
| **ChildTaskFields** | [Dictionary&lt;string, FieldMapping&gt;](FieldMapping.md) | Required | Field Mappings |
| **MapStackingKeyFrom** | **string** | Optional | The field to be mapped as the ChildTasks Stacking Key |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ResultantChildTaskConfiguration(
    resultMatchingPattern: new ResultMatchingPattern(...),  // optional
    taskDefinitionId: new ResourceId(...),  // required
    taskDefinitionAsAt: DateTimeOffset.Now,  // optional — TaskDefinition AsAt timestamp
    initialTrigger: "...",  // optional — The Initial Trigger for automatic start
    childTaskFields: new FieldMapping(...),  // required — Field Mappings
    mapStackingKeyFrom: "..."  // optional — The field to be mapped as the ChildTasks Stacking Key
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResultantChildTaskConfiguration>(json);
```


## Related Models

- [ResultMatchingPattern](ResultMatchingPattern.md)
- [ResourceId](ResourceId.md)
- [FieldMapping](FieldMapping.md) — used in `ChildTaskFields`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

