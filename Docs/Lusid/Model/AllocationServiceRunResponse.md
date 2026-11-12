# Finbourne.Sdk.Lusid.Model.AllocationServiceRunResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | The placements that were allocated successfully. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The placements that could not be allocated, keyed by placement, with the reason. |
| **Allocations** | [List&lt;AllocationServiceRunAllocation&gt;](AllocationServiceRunAllocation.md) | Optional | Every allocation the run touched across the successful placements, each with its outcome. |
| **Warnings** | [List&lt;AllocationServiceRunWarning&gt;](AllocationServiceRunWarning.md) | Optional | Warnings raised while allocating the successful placements. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationServiceRunResponse(
    values: new List<ResourceId>(),  // optional — The placements that were allocated successfully.
    failed: new ErrorDetail(...),  // optional — The placements that could not be allocated, keyed by placement, with the reason.
    allocations: new List<AllocationServiceRunAllocation>(),  // optional — Every allocation the run touched across the successful placements, each with its outcome.
    warnings: new List<AllocationServiceRunWarning>()  // optional — Warnings raised while allocating the successful placements.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationServiceRunResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [AllocationServiceRunAllocation](AllocationServiceRunAllocation.md) — used in `Allocations`
- [AllocationServiceRunWarning](AllocationServiceRunWarning.md) — used in `Warnings`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

