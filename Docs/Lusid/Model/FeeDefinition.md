# Finbourne.Sdk.Lusid.Model.FeeDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FeeCode** | **string** | Required | *No description available.* |
| **Basis** | **string** | Required | Available values: CommittedCapital, InvestedCapital, NetInvestedCapital, Nav. |
| **Rate** | **decimal?** | Optional | *No description available.* |
| **Tiers** | [List&lt;FeeSizeTier&gt;](FeeSizeTier.md) | Optional | *No description available.* |
| **DayCountConvention** | **string** | Optional | *No description available.* |
| **StepDown** | [FeeStepDown](FeeStepDown.md) | Optional | *No description available.* |
| **OffsetPercentage** | **decimal?** | Optional | *No description available.* |
| **WaiverPercentage** | **decimal?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FeeDefinition(
    feeCode: "...",  // required
    basis: "...",  // required — Available values: CommittedCapital, InvestedCapital, NetInvestedCapital, Nav.
    rate: 0.0d,  // optional
    tiers: new List<FeeSizeTier>(),  // optional
    dayCountConvention: "...",  // optional
    stepDown: new FeeStepDown(...),  // optional
    offsetPercentage: 0.0d,  // optional
    waiverPercentage: 0.0d  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FeeDefinition>(json);
```

- [FeeSizeTier](FeeSizeTier.md)
- [FeeStepDown](FeeStepDown.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

