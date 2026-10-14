# Finbourne.Sdk.Lusid.Model.CapabilityOverride

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Capability** | **string** | Required | Available values: RecallableDistributions, RecallCalls, ReturnOfExcessContributions, SubsequentCloseEqualisation, PartnerPnlAllocation, DistributionMechanism, DistributionCharacterSource, SecondaryTransfer, ExcuseExclude, DealScopedPnl, NettedCallAndDistribution. |
| **Setting** | **string** | Required | Available values: Allowed, Forbidden. |
| **Reason** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CapabilityOverride(
    capability: "...",  // required — Available values: RecallableDistributions, RecallCalls, ReturnOfExcessContributions, SubsequentCloseEqualisation, PartnerPnlAllocation, DistributionMechanism, DistributionCharacterSource, SecondaryTransfer, ExcuseExclude, DealScopedPnl, NettedCallAndDistribution.
    setting: "...",  // required — Available values: Allowed, Forbidden.
    reason: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CapabilityOverride>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

