# Finbourne.Sdk.Lusid.Model.ApportionmentBreakdown

The apportionment result for one level - the fund (apportioning the non-class-specific P&L across all  share classes) or a single allocation group (apportioning its tagged P&L across its members) - with the  per-member base values and factors the method produced.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ApportionmentLevel** | **string** | Required | Whether this result is the fund-level apportionment (across all share classes) or an allocation group&#39;s (across its share classes). Available values: Fund, AllocationGroup. |
| **AllocationGroupCode** | **string** | Optional | The ShareClassShortCode identifying the allocation group this result is for, or null for the fund-level result. |
| **ApportionmentMethodPropertyKey** | **string** | Required | The apportionment method property key that produced the factors. |
| **Factors** | [List&lt;ApportionmentMemberFactor&gt;](ApportionmentMemberFactor.md) | Required | The per-member base values and apportionment factors produced by the method. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ApportionmentBreakdown(
    apportionmentLevel: "...",  // required — Whether this result is the fund-level apportionment (across all share classes) or an allocation group&#39;s (across its share classes). Available values: Fund, AllocationGroup.
    allocationGroupCode: "...",  // optional — The ShareClassShortCode identifying the allocation group this result is for, or null for the fund-level result.
    apportionmentMethodPropertyKey: "...",  // required — The apportionment method property key that produced the factors.
    factors: new List<ApportionmentMemberFactor>()  // required — The per-member base values and apportionment factors produced by the method.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ApportionmentBreakdown>(json);
```

- [ApportionmentMemberFactor](ApportionmentMemberFactor.md) — used in `Factors`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

