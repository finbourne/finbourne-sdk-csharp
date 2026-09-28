# Finbourne.Sdk.Lusid.Model.AllocationMapBasis

How an allocation event is weighted between the participants of an Allocation Map.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Kind** | **string** | Optional | How the event is weighted between the participants. ValueWeighted apportions pro rata to each participant&#39;s value; PropertyWeighted apportions pro rata to the property named in &#39;property&#39;; FixedPercentage apportions by the factors in fixedFactors. Available values: ValueWeighted, PropertyWeighted, FixedPercentage. |
| **Property** | [ApportionmentMethodProperty](ApportionmentMethodProperty.md) | Optional | *No description available.* |
| **FixedFactors** | [List&lt;AllocationMapFixedFactor&gt;](AllocationMapFixedFactor.md) | Optional | For a FixedPercentage basis, the share of the amount each participating investor record takes. At least one is required under that kind, every factor must be positive, and the factors must sum to 1. |
| **ScopedToMember** | **bool** | Optional | Whether the basis is evaluated only over amounts booked against the structure member rather than fund-wide. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationMapBasis(
    kind: "...",  // optional — How the event is weighted between the participants. ValueWeighted apportions pro rata to each participant&#39;s value; PropertyWeighted apportions pro rata to the property named in &#39;property&#39;; FixedPercentage apportions by the factors in fixedFactors. Available values: ValueWeighted, PropertyWeighted, FixedPercentage.
    property: new ApportionmentMethodProperty(...),  // optional
    fixedFactors: new List<AllocationMapFixedFactor>(),  // optional — For a FixedPercentage basis, the share of the amount each participating investor record takes. At least one is required under that kind, every factor must be positive, and the factors must sum to 1.
    scopedToMember: true  // optional — Whether the basis is evaluated only over amounts booked against the structure member rather than fund-wide.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationMapBasis>(json);
```

- [ApportionmentMethodProperty](ApportionmentMethodProperty.md)
- [AllocationMapFixedFactor](AllocationMapFixedFactor.md) — used in `FixedFactors`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

