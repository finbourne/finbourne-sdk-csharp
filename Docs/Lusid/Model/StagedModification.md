# Finbourne.Sdk.Lusid.Model.StagedModification

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Optional | The unique Id for the staged modification |
| **AsAtStaged** | **DateTimeOffset** | Optional | Time at which the modification was staged. |
| **UserIdStaged** | **string** | Optional | Id of the user who created the stage modification request. |
| **RequestedIdStaged** | **string** | Optional | The Request Id that initiated this staged modification. |
| **RequestReason** | **string** | Optional | The Request Reason from the context that initiated this staged modification. |
| **Action** | **string** | Optional | Type of action of the staged modification, either create, update or delete. |
| **StagingRule** | [StagedModificationStagingRule](StagedModificationStagingRule.md) | Optional | *No description available.* |
| **Decisions** | [List&lt;StagedModificationDecision&gt;](StagedModificationDecision.md) | Optional | Object containing information relating to the decision on the staged modification. |
| **DecisionsCount** | **int** | Optional | Number of decisions made. |
| **Status** | **string** | Optional | The status of the staged modification. |
| **AsAtClosed** | **DateTimeOffset?** | Optional | Time at which the modification was closed by either rejection or approval. |
| **EntityType** | **string** | Optional | The type of the entity that the staged modification applies to. |
| **Scope** | **string** | Optional | The scope of the entity that this staged modification applies to. |
| **EntityUniqueId** | **string** | Optional | The unique Id of the entity the staged modification applies to. |
| **RequestedChanges** | [RequestedChanges](RequestedChanges.md) | Optional | *No description available.* |
| **EntityHrefs** | [StagedModificationsEntityHrefs](StagedModificationsEntityHrefs.md) | Optional | *No description available.* |
| **DisplayName** | **string** | Optional | The display name of the entity the staged modification applies to. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StagedModification(
    id: "...",  // optional — The unique Id for the staged modification
    asAtStaged: DateTimeOffset.Now,  // optional — Time at which the modification was staged.
    userIdStaged: "...",  // optional — Id of the user who created the stage modification request.
    requestedIdStaged: "...",  // optional — The Request Id that initiated this staged modification.
    requestReason: "...",  // optional — The Request Reason from the context that initiated this staged modification.
    action: "...",  // optional — Type of action of the staged modification, either create, update or delete.
    stagingRule: new StagedModificationStagingRule(...),  // optional
    decisions: new List<StagedModificationDecision>(),  // optional — Object containing information relating to the decision on the staged modification.
    decisionsCount: 0,  // optional — Number of decisions made.
    status: "...",  // optional — The status of the staged modification.
    asAtClosed: DateTimeOffset.Now,  // optional — Time at which the modification was closed by either rejection or approval.
    entityType: "...",  // optional — The type of the entity that the staged modification applies to.
    scope: "...",  // optional — The scope of the entity that this staged modification applies to.
    entityUniqueId: "...",  // optional — The unique Id of the entity the staged modification applies to.
    requestedChanges: new RequestedChanges(...),  // optional
    entityHrefs: new StagedModificationsEntityHrefs(...),  // optional
    displayName: "...",  // optional — The display name of the entity the staged modification applies to.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StagedModification>(json);
```

- [StagedModificationStagingRule](StagedModificationStagingRule.md)
- [StagedModificationDecision](StagedModificationDecision.md) — used in `Decisions`
- [RequestedChanges](RequestedChanges.md)
- [StagedModificationsEntityHrefs](StagedModificationsEntityHrefs.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

