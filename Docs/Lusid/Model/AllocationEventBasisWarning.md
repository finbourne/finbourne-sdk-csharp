# Finbourne.Sdk.Lusid.Model.AllocationEventBasisWarning

One thing the basis source had to work around when it read the register for an Allocation Event.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Optional | The warning, for example MissingFeeRate or RoundingPartnerNotParticipant. |
| **InvestorRecordId** | **string** | Optional | The investor record the warning concerns, or absent when it concerns the event as a whole. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventBasisWarning(
    code: "...",  // optional — The warning, for example MissingFeeRate or RoundingPartnerNotParticipant.
    investorRecordId: "..."  // optional — The investor record the warning concerns, or absent when it concerns the event as a whole.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventBasisWarning>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

