# Finbourne.Sdk.Lusid.Model.ScenarioPreviewResponse

The result of previewing a scenario: every market data target the scenario's shifts changed, with  values before and after, plus warnings for market data that matched a shift but could not honour it.  An empty applied list means the scenario would touch nothing for this portfolio and recipe.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Applied** | [List&lt;ScenarioPreviewAppliedShift&gt;](ScenarioPreviewAppliedShift.md) | Optional | One entry per market data target changed by a shift. |
| **Skipped** | **List&lt;string&gt;** | Optional | Market data that matched a shift but was skipped (e.g. an element type that does not support  transformation), with the reason. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ScenarioPreviewResponse(
    applied: new List<ScenarioPreviewAppliedShift>(),  // optional — One entry per market data target changed by a shift.
    skipped:   // optional — Market data that matched a shift but was skipped (e.g. an element type that does not support  transformation), with the reason.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScenarioPreviewResponse>(json);
```


## Related Models

- [ScenarioPreviewAppliedShift](ScenarioPreviewAppliedShift.md) — used in `Applied`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

