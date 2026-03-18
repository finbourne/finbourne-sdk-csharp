# Finbourne.Sdk.Lusid.Model.StagedModificationsInfo

The staged modifications metadata.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CountPending** | **int** | Required | The number of staged modifications for the entity with a status of Pending for the requested asAt. |
| **HrefPending** | **string** | Required | Link to the list staged modifications endpoint, filtered by entityType, entityUniqueId and status (&#x3D; Pending). |
| **IdsPreviewed** | **List&lt;string&gt;** | Optional | An array of the ids of any StagedModifications being previewed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StagedModificationsInfo(
    countPending: 0,  // required — The number of staged modifications for the entity with a status of Pending for the requested asAt.
    hrefPending: "...",  // required — Link to the list staged modifications endpoint, filtered by entityType, entityUniqueId and status (&#x3D; Pending).
    idsPreviewed:   // optional — An array of the ids of any StagedModifications being previewed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StagedModificationsInfo>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

