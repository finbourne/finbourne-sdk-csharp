# Finbourne.Sdk.Lusid.Model.AllocationPostingPlan

Everything booking an Allocation Event writes, in write order: the investors' lines, the roll-ups above them and  the fund side. Returned by a dry run, so a caller sees exactly what a booking would post before it does.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LpSide** | [List&lt;AllocationPostingLpLine&gt;](AllocationPostingLpLine.md) | Optional | The instrument events written on each investor&#39;s commitment line, one per component. |
| **RollUps** | [List&lt;AllocationPostingRollUp&gt;](AllocationPostingRollUp.md) | Optional | The roll-ups written on each vehicle&#39;s line on the register above it, summing the lines beneath. |
| **FundSide** | [List&lt;AllocationPostingFundLine&gt;](AllocationPostingFundLine.md) | Optional | The transactions written on the fund&#39;s own books. |
| **Counts** | [AllocationPostingCounts](AllocationPostingCounts.md) | Optional | *No description available.* |
| **Warnings** | [List&lt;AllocationEventBookingWarning&gt;](AllocationEventBookingWarning.md) | Optional | The validation rules the booking would be allowed to proceed through under the map&#39;s policy. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationPostingPlan(
    lpSide: new List<AllocationPostingLpLine>(),  // optional — The instrument events written on each investor&#39;s commitment line, one per component.
    rollUps: new List<AllocationPostingRollUp>(),  // optional — The roll-ups written on each vehicle&#39;s line on the register above it, summing the lines beneath.
    fundSide: new List<AllocationPostingFundLine>(),  // optional — The transactions written on the fund&#39;s own books.
    counts: new AllocationPostingCounts(...),  // optional
    warnings: new List<AllocationEventBookingWarning>()  // optional — The validation rules the booking would be allowed to proceed through under the map&#39;s policy.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationPostingPlan>(json);
```


## Related Models

- [AllocationPostingLpLine](AllocationPostingLpLine.md) — used in `LpSide`
- [AllocationPostingRollUp](AllocationPostingRollUp.md) — used in `RollUps`
- [AllocationPostingFundLine](AllocationPostingFundLine.md) — used in `FundSide`
- [AllocationPostingCounts](AllocationPostingCounts.md)
- [AllocationEventBookingWarning](AllocationEventBookingWarning.md) — used in `Warnings`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

