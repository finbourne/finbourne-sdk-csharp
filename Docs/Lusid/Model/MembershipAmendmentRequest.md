# Finbourne.Sdk.Lusid.Model.MembershipAmendmentRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CustomDataModelId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **EntityType** | **string** | Required | The type of the entity that is being added or removed from the Custom Data Model. |
| **EntityUniqueId** | **string** | Required | The entity unique identifier of the entity that is being added or removed from the Custom Data Model. |
| **Operation** | **string** | Required | The operation to be performed on the entity&#39;s membership in the Custom Data Model. Either &#39;Add&#39; or &#39;Remove&#39;. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MembershipAmendmentRequest(
    customDataModelId: new ResourceId(...),  // required
    entityType: "...",  // required — The type of the entity that is being added or removed from the Custom Data Model.
    entityUniqueId: "...",  // required — The entity unique identifier of the entity that is being added or removed from the Custom Data Model.
    operation: "..."  // required — The operation to be performed on the entity&#39;s membership in the Custom Data Model. Either &#39;Add&#39; or &#39;Remove&#39;.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MembershipAmendmentRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

