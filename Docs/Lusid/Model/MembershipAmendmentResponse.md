# Finbourne.Sdk.Lusid.Model.MembershipAmendmentResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CustomDataModelId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **EntityType** | **string** | Required | The type of the entity that was added or removed from the Custom Data Model. |
| **EntityUniqueId** | **string** | Required | The entity unique identifier of the entity that was added or removed from the Custom Data Model. |
| **Operation** | **string** | Required | The operation that was performed on the entity&#39;s membership in the Custom Data Model. Either &#39;Add&#39; or &#39;Remove&#39;. |
| **EntityDisplayName** | **string** | Required | The display name of the entity that was added or removed from the Custom Data Model. |
| **DataModelMembership** | [DataModelMembership](DataModelMembership.md) | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **StagedModifications** | [StagedModificationsInfo](StagedModificationsInfo.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MembershipAmendmentResponse(
    customDataModelId: new ResourceId(...),  // required
    entityType: "...",  // required — The type of the entity that was added or removed from the Custom Data Model.
    entityUniqueId: "...",  // required — The entity unique identifier of the entity that was added or removed from the Custom Data Model.
    operation: "...",  // required — The operation that was performed on the entity&#39;s membership in the Custom Data Model. Either &#39;Add&#39; or &#39;Remove&#39;.
    entityDisplayName: "...",  // required — The display name of the entity that was added or removed from the Custom Data Model.
    dataModelMembership: new DataModelMembership(...),  // optional
    varVersion: new ModelVersion(...),  // optional
    stagedModifications: new StagedModificationsInfo(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MembershipAmendmentResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [DataModelMembership](DataModelMembership.md)
- [ModelVersion](ModelVersion.md)
- [StagedModificationsInfo](StagedModificationsInfo.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

