# Finbourne.Sdk.Lusid.Model.UpdateRelationshipDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The display name of the relation. |
| **OutwardDescription** | **string** | Required | The description to relate source entity object and target entity object. |
| **InwardDescription** | **string** | Required | The description to relate target entity object and source entity object. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateRelationshipDefinitionRequest(
    displayName: "...",  // required — The display name of the relation.
    outwardDescription: "...",  // required — The description to relate source entity object and target entity object.
    inwardDescription: "..."  // required — The description to relate target entity object and source entity object.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateRelationshipDefinitionRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

