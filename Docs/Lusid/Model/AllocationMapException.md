# Finbourne.Sdk.Lusid.Model.AllocationMapException

A departure from the default participation of an Allocation Map for one investor record.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Required | The investor record the exception applies to. |
| **Treatment** | **string** | Required | What the exception does. Excluded removes the investor record from every allocation; FixedPercentage gives it participationPercent of each event off the top, before the remainder is shared pro rata between the other participants. Available values: Excluded, FixedPercentage. |
| **ParticipationPercent** | **decimal?** | Optional | For a FixedPercentage exception, the fixed share as a fraction in the range (0, 1]. Not allowed on an Excluded exception. The fixed shares of all exceptions may not sum to more than 1. |
| **Reason** | **string** | Required | Why the exception exists, for example a side letter or regulatory restriction. Required. |
| **EffectiveFrom** | **DateTimeOffset?** | Optional | The datetime from which the exception is in force. Defaults to always if not specified. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationMapException(
    investorRecordId: "...",  // required — The investor record the exception applies to.
    treatment: "...",  // required — What the exception does. Excluded removes the investor record from every allocation; FixedPercentage gives it participationPercent of each event off the top, before the remainder is shared pro rata between the other participants. Available values: Excluded, FixedPercentage.
    participationPercent: 0.0d,  // optional — For a FixedPercentage exception, the fixed share as a fraction in the range (0, 1]. Not allowed on an Excluded exception. The fixed shares of all exceptions may not sum to more than 1.
    reason: "...",  // required — Why the exception exists, for example a side letter or regulatory restriction. Required.
    effectiveFrom: DateTimeOffset.Now  // optional — The datetime from which the exception is in force. Defaults to always if not specified.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationMapException>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

