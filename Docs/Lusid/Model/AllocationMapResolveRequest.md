# Finbourne.Sdk.Lusid.Model.AllocationMapResolveRequest

A dry run of an Allocation Map: the event to share, and the basis values to share it by.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EventType** | **string** | Required | The kind of allocation event to resolve: CapitalCall, Distribution, FeeExpense or ValuationMove. The map must define a basis for it. Available values: CapitalCall, Distribution, FeeExpense, ValuationMove. |
| **Amount** | **decimal** | Required | The amount of the event to share between the participants, in the event currency. |
| **Currency** | **string** | Required | The currency of the amount. |
| **BasisValues** | [List&lt;AllocationMapBasisValue&gt;](AllocationMapBasisValue.md) | Optional | For a ValueWeighted or PropertyWeighted basis, the basis value of each participating investor record, supplied by the caller until investor records are read from LUSID. Under the AllCommittedToMembers rule these also name the committed investor records. Not needed for a FixedPercentage basis. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationMapResolveRequest(
    eventType: "...",  // required — The kind of allocation event to resolve: CapitalCall, Distribution, FeeExpense or ValuationMove. The map must define a basis for it. Available values: CapitalCall, Distribution, FeeExpense, ValuationMove.
    amount: 0.0d,  // required — The amount of the event to share between the participants, in the event currency.
    currency: "...",  // required — The currency of the amount.
    basisValues: new List<AllocationMapBasisValue>()  // optional — For a ValueWeighted or PropertyWeighted basis, the basis value of each participating investor record, supplied by the caller until investor records are read from LUSID. Under the AllCommittedToMembers rule these also name the committed investor records. Not needed for a FixedPercentage basis.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationMapResolveRequest>(json);
```

- [AllocationMapBasisValue](AllocationMapBasisValue.md) — used in `BasisValues`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

