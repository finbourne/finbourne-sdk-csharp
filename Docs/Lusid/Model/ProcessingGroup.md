# Finbourne.Sdk.Lusid.Model.ProcessingGroup

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Optional | The name of the Processing Group. |
| **Description** | **string** | Optional | A description for the Processing Group. |
| **Schedule** | [ProcessingGroupSchedule](ProcessingGroupSchedule.md) | Optional | *No description available.* |
| **ReferenceListId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **WorkflowId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **ResolvedReferenceList** | [ReferenceList](ReferenceList.md) | Optional | *No description available.* |
| **ListExceptionFilter** | **string** | Optional | A filter selecting reference list items to exclude whenever this Processing Group resolves its reference list. Optional. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ProcessingGroup(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    id: new ResourceId(...),  // required
    displayName: "...",  // optional — The name of the Processing Group.
    description: "...",  // optional — A description for the Processing Group.
    schedule: new ProcessingGroupSchedule(...),  // optional
    referenceListId: new ResourceId(...),  // optional
    workflowId: new ResourceId(...),  // optional
    resolvedReferenceList: new ReferenceList(...),  // optional
    listExceptionFilter: "...",  // optional — A filter selecting reference list items to exclude whenever this Processing Group resolves its reference list. Optional.
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ProcessingGroup>(json);
```

- [ResourceId](ResourceId.md)
- [ProcessingGroupSchedule](ProcessingGroupSchedule.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ReferenceList](ReferenceList.md)
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

