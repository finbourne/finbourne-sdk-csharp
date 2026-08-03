# Finbourne.Sdk.Lusid.Model.ScenarioPreviewAppliedShift

One market data target changed by one scenario shift.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveAt** | **DateTimeOffset** | Optional | The effective date of the market data the shift was applied to. |
| **Shift** | **string** | Optional | Description of the shift, e.g. \&quot;EquityShift on &#39;SCENARIO_EQUITY&#39;\&quot;. |
| **Target** | **string** | Optional | Description of the market data target the shift changed. |
| **ValueBefore** | **decimal?** | Optional | The target&#39;s value before the shift. Null for multi-point targets (e.g. whole curves) where a  single number is not meaningful. |
| **ValueAfter** | **decimal?** | Optional | The target&#39;s value after the shift. Null for multi-point targets. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ScenarioPreviewAppliedShift(
    effectiveAt: DateTimeOffset.Now,  // optional — The effective date of the market data the shift was applied to.
    shift: "...",  // optional — Description of the shift, e.g. \&quot;EquityShift on &#39;SCENARIO_EQUITY&#39;\&quot;.
    target: "...",  // optional — Description of the market data target the shift changed.
    valueBefore: 0.0d,  // optional — The target&#39;s value before the shift. Null for multi-point targets (e.g. whole curves) where a  single number is not meaningful.
    valueAfter: 0.0d  // optional — The target&#39;s value after the shift. Null for multi-point targets.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScenarioPreviewAppliedShift>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

