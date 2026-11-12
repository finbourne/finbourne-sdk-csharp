# Finbourne.Sdk.Lusid.Model.MarginRunAllocation

How far the allocation pass over a run's base calls got: whether it ran, how many calls it proposed collateral  for, and what it left out.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Status** | **string** | Required | How far the allocation pass got. One of Pending, Completed, Skipped or Failed. |
| **AllocatedCallCount** | **int** | Required | How many calls the pass proposed collateral for. |
| **Detail** | **string** | Optional | Which calls the pass could not allocate and why, or why it failed. Null when every call that moves our collateral was allocated. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarginRunAllocation(
    status: "...",  // required — How far the allocation pass got. One of Pending, Completed, Skipped or Failed.
    allocatedCallCount: 0,  // required — How many calls the pass proposed collateral for.
    detail: "..."  // optional — Which calls the pass could not allocate and why, or why it failed. Null when every call that moves our collateral was allocated.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarginRunAllocation>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

