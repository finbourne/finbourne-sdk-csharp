# Finbourne.Sdk.Lusid.Model.AllocationMapResolution

The result of resolving an Allocation Map for one event: how much each investor record receives, and why.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EventType** | **string** | Optional | The kind of allocation event that was resolved. Available values: CapitalCall, Distribution, FeeExpense, ValuationMove. |
| **Amount** | **decimal** | Optional | The amount that was shared. |
| **Currency** | **string** | Optional | The currency of the amount. |
| **BasisRule** | **string** | Optional | The basis the map applies to this event type. Available values: ValueWeighted, PropertyWeighted, FixedPercentage. |
| **BasisPool** | **decimal** | Optional | The sum of the basis values over the participants that share the remainder pro rata. |
| **FixedTotal** | **decimal** | Optional | The total taken off the top by FixedPercentage exceptions before the remainder is shared. |
| **ParticipantCount** | **int** | Optional | The number of investor records that receive a share, whether fixed or pro rata. |
| **ExcludedCount** | **int** | Optional | The number of investor records an exception removed from the allocation. |
| **Allocations** | [List&lt;AllocationMapAllocation&gt;](AllocationMapAllocation.md) | Optional | The share of each investor record, including those excluded, which receive nothing. |
| **Reconciles** | **bool** | Optional | Whether the allocated amounts sum exactly to the requested amount. Amounts are rounded to two decimal places with the largest-remainder method, so an amount with more decimal places does not reconcile. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationMapResolution(
    eventType: "...",  // optional — The kind of allocation event that was resolved. Available values: CapitalCall, Distribution, FeeExpense, ValuationMove.
    amount: 0.0d,  // optional — The amount that was shared.
    currency: "...",  // optional — The currency of the amount.
    basisRule: "...",  // optional — The basis the map applies to this event type. Available values: ValueWeighted, PropertyWeighted, FixedPercentage.
    basisPool: 0.0d,  // optional — The sum of the basis values over the participants that share the remainder pro rata.
    fixedTotal: 0.0d,  // optional — The total taken off the top by FixedPercentage exceptions before the remainder is shared.
    participantCount: 0,  // optional — The number of investor records that receive a share, whether fixed or pro rata.
    excludedCount: 0,  // optional — The number of investor records an exception removed from the allocation.
    allocations: new List<AllocationMapAllocation>(),  // optional — The share of each investor record, including those excluded, which receive nothing.
    reconciles: true  // optional — Whether the allocated amounts sum exactly to the requested amount. Amounts are rounded to two decimal places with the largest-remainder method, so an amount with more decimal places does not reconcile.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationMapResolution>(json);
```

- [AllocationMapAllocation](AllocationMapAllocation.md) — used in `Allocations`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

