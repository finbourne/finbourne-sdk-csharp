# Finbourne.Sdk.Lusid.Model.AllocationMapEventBasis

The basis an Allocation Map applies to one kind of allocation event.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EventType** | **string** | Required | The kind of allocation event the basis applies to: CapitalCall, Distribution, FeeExpense, ValuationMove, Equalisation, RecallExpiry, Transfer, Default, Commitment or DealFunding. Available values: CapitalCall, Distribution, FeeExpense, ValuationMove, Commitment, Equalisation, RecallExpiry, Transfer, Default, DealFunding. |
| **Basis** | [AllocationMapBasis](AllocationMapBasis.md) | Required | *No description available.* |
| **Component** | **string** | Optional | The component of the event the basis applies to, for example MgmtFee or OrgCost. Absent means the entry is the default for every component of the event type without an entry of its own. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationMapEventBasis(
    eventType: "...",  // required — The kind of allocation event the basis applies to: CapitalCall, Distribution, FeeExpense, ValuationMove, Equalisation, RecallExpiry, Transfer, Default, Commitment or DealFunding. Available values: CapitalCall, Distribution, FeeExpense, ValuationMove, Commitment, Equalisation, RecallExpiry, Transfer, Default, DealFunding.
    basis: new AllocationMapBasis(...),  // required
    component: "..."  // optional — The component of the event the basis applies to, for example MgmtFee or OrgCost. Absent means the entry is the default for every component of the event type without an entry of its own.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationMapEventBasis>(json);
```

- [AllocationMapBasis](AllocationMapBasis.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

