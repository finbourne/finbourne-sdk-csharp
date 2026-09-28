# Finbourne.Sdk.Lusid.Model.AllocationMapRequest

The request used to create or update an Allocation Map.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code of the Allocation Map. |
| **Name** | **string** | Required | The display name of the Allocation Map. |
| **Description** | **string** | Optional | An optional description for the Allocation Map. |
| **StructureMemberId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **InheritsFrom** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Participants** | [AllocationMapParticipants](AllocationMapParticipants.md) | Optional | *No description available.* |
| **BasisByEventType** | [List&lt;AllocationMapEventBasis&gt;](AllocationMapEventBasis.md) | Optional | The basis on which each kind of allocation event is shared between the participants. At most one entry per event type. |
| **EffectiveAt** | **DateTimeOffset?** | Optional | The effective datetime from which the Allocation Map applies. Defaults to the beginning of time if not specified, so that the map is visible at every effective datetime. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationMapRequest(
    code: "...",  // required — The code of the Allocation Map.
    name: "...",  // required — The display name of the Allocation Map.
    description: "...",  // optional — An optional description for the Allocation Map.
    structureMemberId: new ResourceId(...),  // required
    inheritsFrom: new ResourceId(...),  // optional
    participants: new AllocationMapParticipants(...),  // optional
    basisByEventType: new List<AllocationMapEventBasis>(),  // optional — The basis on which each kind of allocation event is shared between the participants. At most one entry per event type.
    effectiveAt: DateTimeOffset.Now  // optional — The effective datetime from which the Allocation Map applies. Defaults to the beginning of time if not specified, so that the map is visible at every effective datetime.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationMapRequest>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [AllocationMapParticipants](AllocationMapParticipants.md)
- [AllocationMapEventBasis](AllocationMapEventBasis.md) — used in `BasisByEventType`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

