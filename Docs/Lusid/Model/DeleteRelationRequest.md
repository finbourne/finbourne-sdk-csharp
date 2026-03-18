# Finbourne.Sdk.Lusid.Model.DeleteRelationRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SourceEntityId** | **Dictionary&lt;string, string&gt;** | Required | The identifier of the source entity of the relation to be deleted. |
| **TargetEntityId** | **Dictionary&lt;string, string&gt;** | Required | The identifier of the target entity of the relation to be deleted. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DeleteRelationRequest(
    sourceEntityId: ,  // required — The identifier of the source entity of the relation to be deleted.
    targetEntityId:   // required — The identifier of the target entity of the relation to be deleted.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DeleteRelationRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

