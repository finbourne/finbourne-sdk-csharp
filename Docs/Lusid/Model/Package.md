# Finbourne.Sdk.Lusid.Model.Package

A structure used to describe the structure of an order or orders that make up a non-trivial trade.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **OrderIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | Related order ids. |
| **OrderInstructionIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | Related order instruction ids. |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Client-defined properties associated with this execution. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **DataModelMembership** | [DataModelMembership](DataModelMembership.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Package(
    id: new ResourceId(...),  // required
    orderIds: new List<ResourceId>(),  // required — Related order ids.
    orderInstructionIds: new List<ResourceId>(),  // required — Related order instruction ids.
    properties: new PerpetualProperty(...),  // optional — Client-defined properties associated with this execution.
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
var instance = JsonConvert.DeserializeObject<Package>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md) — used in `OrderIds`
- [ResourceId](ResourceId.md) — used in `OrderInstructionIds`
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)
- [DataModelMembership](DataModelMembership.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

