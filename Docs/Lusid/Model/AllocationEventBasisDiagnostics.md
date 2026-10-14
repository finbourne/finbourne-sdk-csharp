# Finbourne.Sdk.Lusid.Model.AllocationEventBasisDiagnostics

What the basis source found when it read the register for an Allocation Event.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ParticipantCount** | **int** | Optional | The number of investor records whose basis values were read. |
| **Excluded** | **List&lt;string&gt;** | Optional | The investor records the map&#39;s exceptions kept out of the event. |
| **Warnings** | [List&lt;AllocationEventBasisWarning&gt;](AllocationEventBasisWarning.md) | Optional | Anything the source had to work around, for example MissingFeeRate on a line without a management fee rate. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventBasisDiagnostics(
    participantCount: 0,  // optional — The number of investor records whose basis values were read.
    excluded: ,  // optional — The investor records the map&#39;s exceptions kept out of the event.
    warnings: new List<AllocationEventBasisWarning>()  // optional — Anything the source had to work around, for example MissingFeeRate on a line without a management fee rate.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventBasisDiagnostics>(json);
```

- [AllocationEventBasisWarning](AllocationEventBasisWarning.md) — used in `Warnings`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

