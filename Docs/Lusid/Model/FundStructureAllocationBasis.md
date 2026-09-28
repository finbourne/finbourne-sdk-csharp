# Finbourne.Sdk.Lusid.Model.FundStructureAllocationBasis

The default apportionment basis of a Fund Structure member.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Kind** | **string** | Optional | How the apportionment is weighted. ValueWeighted apportions pro rata to each investing member&#39;s value; PropertyWeighted apportions pro rata to the property named in &#39;property&#39;; FixedPercentage defers to factors held on an allocation map. A ValueWeighted basis is rejected where a holder of this member also holds an unrelated member, because the member could not be finalised before that sibling is valued. Available values: ValueWeighted, PropertyWeighted, FixedPercentage. |
| **Property** | [ApportionmentMethodProperty](ApportionmentMethodProperty.md) | Optional | *No description available.* |
| **ScopedToMember** | **bool** | Optional | Whether the basis is evaluated only over amounts booked against this member rather than fund-wide. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundStructureAllocationBasis(
    kind: "...",  // optional — How the apportionment is weighted. ValueWeighted apportions pro rata to each investing member&#39;s value; PropertyWeighted apportions pro rata to the property named in &#39;property&#39;; FixedPercentage defers to factors held on an allocation map. A ValueWeighted basis is rejected where a holder of this member also holds an unrelated member, because the member could not be finalised before that sibling is valued. Available values: ValueWeighted, PropertyWeighted, FixedPercentage.
    property: new ApportionmentMethodProperty(...),  // optional
    scopedToMember: true  // optional — Whether the basis is evaluated only over amounts booked against this member rather than fund-wide.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundStructureAllocationBasis>(json);
```

- [ApportionmentMethodProperty](ApportionmentMethodProperty.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

