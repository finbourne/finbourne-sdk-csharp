# Finbourne.Sdk.Lusid.Model.AllocationServiceRunWarning

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PlacementId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Code** | **string** | Optional | The kind of warning. One of: OffMinimumIncrement (an allocation&#39;s quantity is not a multiple of the  instrument&#39;s minimum increment), SkippedBooked (an allocation was not changed because transactions are  already booked against it), ExecutionNotAllocated (an execution was excluded from the run). |
| **Message** | **string** | Optional | A description of the warning and, where known, why it arose. |
| **AllocationId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **PortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **ExecutionId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationServiceRunWarning(
    placementId: new ResourceId(...),  // optional
    code: "...",  // optional — The kind of warning. One of: OffMinimumIncrement (an allocation&#39;s quantity is not a multiple of the  instrument&#39;s minimum increment), SkippedBooked (an allocation was not changed because transactions are  already booked against it), ExecutionNotAllocated (an execution was excluded from the run).
    message: "...",  // optional — A description of the warning and, where known, why it arose.
    allocationId: new ResourceId(...),  // optional
    portfolioId: new ResourceId(...),  // optional
    executionId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationServiceRunWarning>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

