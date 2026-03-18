# Finbourne.Sdk.Lusid.Model.AllocationSetRequest

A request to create or update multiple Allocations.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AllocationRequests** | [List&lt;AllocationRequest&gt;](AllocationRequest.md) | Optional | A collection of AllocationRequests. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationSetRequest(
    allocationRequests: new List<AllocationRequest>()  // optional — A collection of AllocationRequests.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationSetRequest>(json);
```


## Related Models

- [AllocationRequest](AllocationRequest.md) — used in `AllocationRequests`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

