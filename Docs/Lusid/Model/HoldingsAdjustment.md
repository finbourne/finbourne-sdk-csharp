# Finbourne.Sdk.Lusid.Model.HoldingsAdjustment

Full content of a holdings adjustment for a single portfolio and effective date.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveAt** | **DateTimeOffset** | Required | The effective datetime from which the adjustment is valid. There can only be one holdings adjustment for a transaction portfolio at a specific effective datetime, so this uniquely identifies the adjustment. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Required | *No description available.* |
| **UnmatchedHoldingMethod** | **string** | Required | Describes how the holdings were adjusted. If &#39;PositionToZero&#39; the entire transaction portfolio&#39;s holdings were set via a call to &#39;Set holdings&#39;. If &#39;KeepTheSame&#39; only the specified holdings were adjusted via a call to &#39;Adjust holdings&#39;. The available values are: PositionToZero, KeepTheSame |
| **Adjustments** | [List&lt;HoldingAdjustment&gt;](HoldingAdjustment.md) | Required | The holding adjustments. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new HoldingsAdjustment(
    effectiveAt: DateTimeOffset.Now,  // required — The effective datetime from which the adjustment is valid. There can only be one holdings adjustment for a transaction portfolio at a specific effective datetime, so this uniquely identifies the adjustment.
    varVersion: new ModelVersion(...),  // required
    unmatchedHoldingMethod: "...",  // required — Describes how the holdings were adjusted. If &#39;PositionToZero&#39; the entire transaction portfolio&#39;s holdings were set via a call to &#39;Set holdings&#39;. If &#39;KeepTheSame&#39; only the specified holdings were adjusted via a call to &#39;Adjust holdings&#39;. The available values are: PositionToZero, KeepTheSame
    adjustments: new List<HoldingAdjustment>(),  // required — The holding adjustments.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<HoldingsAdjustment>(json);
```

- [ModelVersion](ModelVersion.md)
- [HoldingAdjustment](HoldingAdjustment.md) — used in `Adjustments`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

