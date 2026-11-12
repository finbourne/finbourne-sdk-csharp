# Finbourne.Sdk.Lusid.Model.AllocationServiceRunAllocation

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PlacementId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Allocation** | [Allocation](Allocation.md) | Optional | *No description available.* |
| **Outcome** | **string** | Optional | What the run did to this allocation. One of: Created (by this run), Updated (an existing allocation  whose fields changed), Unchanged (an existing allocation the run left as it was), Cancelled (moved to a  cancelled state or reduced to zero quantity), Skipped (left alone because transactions are already booked  against it; see the SkippedBooked warning). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationServiceRunAllocation(
    placementId: new ResourceId(...),  // optional
    allocation: new Allocation(...),  // optional
    outcome: "..."  // optional — What the run did to this allocation. One of: Created (by this run), Updated (an existing allocation  whose fields changed), Unchanged (an existing allocation the run left as it was), Cancelled (moved to a  cancelled state or reduced to zero quantity), Skipped (left alone because transactions are already booked  against it; see the SkippedBooked warning).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationServiceRunAllocation>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [Allocation](Allocation.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

