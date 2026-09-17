# Finbourne.Sdk.Lusid.Model.ReverseStressResponse

The result of a reverse stress solve: the factor the scenario's shifts must be multiplied by to  reach the target loss, together with the whole evaluated ladder so the answer can be checked  rather than taken on trust.                The ladder is part of the answer, not diagnostics. A reverse stress is only meaningful where the  loss moves in one direction with the factor, and the ladder is what shows that it does.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scale** | **decimal?** | Optional | The solved factor: the multiple of the scenario&#39;s shifts that reaches the target. Null when no  factor within the evaluated range reaches it, in which case Converged is false and the  warnings say so. |
| **TargetPnl** | **decimal** | Optional | The change in value that was asked for, echoed back. |
| **AchievedPnl** | **decimal?** | Optional | The change in value actually produced at the solved scale, measured by a valuation at that  factor rather than interpolated. The gap to the target is the honest error of the solve. |
| **BaseValue** | **decimal** | Optional | The unstressed value of the measure over the filtered holdings. |
| **StressedValue** | **decimal?** | Optional | The value of the measure at the solved scale. |
| **Converged** | **bool** | Optional | Whether the achieved change is within the requested tolerance of the target. False means the  reported scale is the best reached, not an answer to rely on. |
| **Method** | **string** | Optional | How the bracketing factor was turned into the reported one: \&quot;Interpolation\&quot; on a monotone  ladder, \&quot;Bisection\&quot; where the ladder turned back on itself and interpolating between one  bracketing pair would have hidden the others. |
| **Valuations** | **int** | Optional | How many valuations the solve ran, the opening ladder counting as one. |
| **Ladder** | [List&lt;ReverseStressRung&gt;](ReverseStressRung.md) | Optional | Every factor evaluated, in increasing order, including the confirming valuations. |
| **Warnings** | **List&lt;string&gt;** | Optional | Anything the caller has to know to read the scale correctly: a non-monotone ladder, a target  out of reach, a solve stopped at the iteration limit. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReverseStressResponse(
    scale: 0.0d,  // optional — The solved factor: the multiple of the scenario&#39;s shifts that reaches the target. Null when no  factor within the evaluated range reaches it, in which case Converged is false and the  warnings say so.
    targetPnl: 0.0d,  // optional — The change in value that was asked for, echoed back.
    achievedPnl: 0.0d,  // optional — The change in value actually produced at the solved scale, measured by a valuation at that  factor rather than interpolated. The gap to the target is the honest error of the solve.
    baseValue: 0.0d,  // optional — The unstressed value of the measure over the filtered holdings.
    stressedValue: 0.0d,  // optional — The value of the measure at the solved scale.
    converged: true,  // optional — Whether the achieved change is within the requested tolerance of the target. False means the  reported scale is the best reached, not an answer to rely on.
    method: "...",  // optional — How the bracketing factor was turned into the reported one: \&quot;Interpolation\&quot; on a monotone  ladder, \&quot;Bisection\&quot; where the ladder turned back on itself and interpolating between one  bracketing pair would have hidden the others.
    valuations: 0,  // optional — How many valuations the solve ran, the opening ladder counting as one.
    ladder: new List<ReverseStressRung>(),  // optional — Every factor evaluated, in increasing order, including the confirming valuations.
    warnings:   // optional — Anything the caller has to know to read the scale correctly: a non-monotone ladder, a target  out of reach, a solve stopped at the iteration limit.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReverseStressResponse>(json);
```

- [ReverseStressRung](ReverseStressRung.md) — used in `Ladder`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

