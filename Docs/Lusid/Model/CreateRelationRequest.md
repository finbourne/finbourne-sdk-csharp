# Finbourne.Sdk.Lusid.Model.CreateRelationRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SourceEntityId** | **Dictionary&lt;string, string&gt;** | Required | The identifier of the source entity. |
| **TargetEntityId** | **Dictionary&lt;string, string&gt;** | Required | The identifier of the target entity. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateRelationRequest(
    sourceEntityId: ,  // required — The identifier of the source entity.
    targetEntityId:   // required — The identifier of the target entity.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateRelationRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

