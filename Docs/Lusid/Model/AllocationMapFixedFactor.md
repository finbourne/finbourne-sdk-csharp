# Finbourne.Sdk.Lusid.Model.AllocationMapFixedFactor

The weight of one investor record under a FixedPercentage basis.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Required | The investor record the factor belongs to. |
| **Factor** | **decimal** | Required | The weight of the investor record. Weights are normalised over the participants that receive the remainder, so they need not sum to 1. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationMapFixedFactor(
    investorRecordId: "...",  // required — The investor record the factor belongs to.
    factor: 0.0d  // required — The weight of the investor record. Weights are normalised over the participants that receive the remainder, so they need not sum to 1.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationMapFixedFactor>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

