# Finbourne.Sdk.Lusid.Model.RankMarginCallRequest

Ranks a margin call's collateral again against the holdings as they stand now, keeping the assets the user chose.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Overrides** | [List&lt;CollateralAllocationOverride&gt;](CollateralAllocationOverride.md) | Optional | The assets and units the user chose, each validated against the agreement&#39;s constraints and kept with its reason when it fails one. Optional. |
| **FillRemainder** | **bool?** | Optional | Whether to fill what the overrides leave uncovered from the ranking, cheapest first. Defaults to true. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RankMarginCallRequest(
    overrides: new List<CollateralAllocationOverride>(),  // optional — The assets and units the user chose, each validated against the agreement&#39;s constraints and kept with its reason when it fails one. Optional.
    fillRemainder: true  // optional — Whether to fill what the overrides leave uncovered from the ranking, cheapest first. Defaults to true.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RankMarginCallRequest>(json);
```


## Related Models

- [CollateralAllocationOverride](CollateralAllocationOverride.md) — used in `Overrides`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

