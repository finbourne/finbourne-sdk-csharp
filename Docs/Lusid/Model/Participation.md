# Finbourne.Sdk.Lusid.Model.Participation

The record an order's participation in a specific placement.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PlacementId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **OrderId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **DataModelMembership** | [DataModelMembership](DataModelMembership.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Participation(
    id: new ResourceId(...),  // required
    placementId: new ResourceId(...),  // required
    orderId: new ResourceId(...),  // required
    varVersion: new ModelVersion(...),  // optional
    dataModelMembership: new DataModelMembership(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Participation>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ModelVersion](ModelVersion.md)
- [DataModelMembership](DataModelMembership.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

