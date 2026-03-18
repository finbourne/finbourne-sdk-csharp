# Finbourne.Sdk.Lusid.Model.CancelledPlacementResult

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PlacementState** | [Placement](Placement.md) | Optional | *No description available.* |
| **CancelledChildPlacements** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | Child placements which have also been cancelled following cancellation of the parent |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CancelledPlacementResult(
    placementState: new Placement(...),  // optional
    cancelledChildPlacements: new List<ResourceId>()  // required — Child placements which have also been cancelled following cancellation of the parent
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CancelledPlacementResult>(json);
```


## Related Models

- [Placement](Placement.md)
- [ResourceId](ResourceId.md) — used in `CancelledChildPlacements`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

