# Finbourne.Sdk.Lusid.Model.ProcessingGroupRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code of the Processing Group. Together with the scope this uniquely identifies the Processing Group. |
| **DisplayName** | **string** | Required | The name of the Processing Group. |
| **Description** | **string** | Optional | A description for the Processing Group. |
| **Schedule** | [ProcessingGroupSchedule](ProcessingGroupSchedule.md) | Required | *No description available.* |
| **ReferenceListId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **WorkflowId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **ListExceptionFilter** | **string** | Optional | A filter selecting reference list items to exclude whenever this Processing Group resolves its reference list. Optional. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ProcessingGroupRequest(
    code: "...",  // required — The code of the Processing Group. Together with the scope this uniquely identifies the Processing Group.
    displayName: "...",  // required — The name of the Processing Group.
    description: "...",  // optional — A description for the Processing Group.
    schedule: new ProcessingGroupSchedule(...),  // required
    referenceListId: new ResourceId(...),  // required
    workflowId: new ResourceId(...),  // optional
    listExceptionFilter: "..."  // optional — A filter selecting reference list items to exclude whenever this Processing Group resolves its reference list. Optional.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ProcessingGroupRequest>(json);
```

- [ProcessingGroupSchedule](ProcessingGroupSchedule.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

