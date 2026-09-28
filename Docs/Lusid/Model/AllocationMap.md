# Finbourne.Sdk.Lusid.Model.AllocationMap

The rules that say which investor records share in the economics of a member of a Fund Structure, and on what basis.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Name** | **string** | Required | The display name of the Allocation Map. |
| **Description** | **string** | Optional | An optional description for the Allocation Map. |
| **StructureMemberId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **InheritsFrom** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Participants** | [AllocationMapParticipants](AllocationMapParticipants.md) | Required | *No description available.* |
| **BasisByEventType** | [List&lt;AllocationMapEventBasis&gt;](AllocationMapEventBasis.md) | Required | The basis on which each kind of allocation event is shared between the participants. At most one entry per event type. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationMap(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    id: new ResourceId(...),  // required
    name: "...",  // required — The display name of the Allocation Map.
    description: "...",  // optional — An optional description for the Allocation Map.
    structureMemberId: new ResourceId(...),  // required
    inheritsFrom: new ResourceId(...),  // optional
    participants: new AllocationMapParticipants(...),  // required
    basisByEventType: new List<AllocationMapEventBasis>(),  // required — The basis on which each kind of allocation event is shared between the participants. At most one entry per event type.
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
var instance = JsonConvert.DeserializeObject<AllocationMap>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [AllocationMapParticipants](AllocationMapParticipants.md)
- [AllocationMapEventBasis](AllocationMapEventBasis.md) — used in `BasisByEventType`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

