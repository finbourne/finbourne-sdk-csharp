# Finbourne.Sdk.Lusid.Model.ScenarioDiagnostics

Diagnostics for the scenario shifts a valuation applied: every market data target changed by a  shift, with values before and after, plus warnings for market data that matched a shift but could  not honour it. Populated whenever the valuation ran with a request-level scenario or  scenario-decorated metrics; null otherwise. The same material is written to the market data  manifest.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Applied** | [List&lt;AppliedScenarioShift&gt;](AppliedScenarioShift.md) | Optional | One entry per market data target changed by a shift. |
| **Skipped** | **List&lt;string&gt;** | Optional | Market data that matched a shift but was skipped (e.g. an element type that does not support  transformation), with the reason. Prefixed with the scenario&#39;s \&quot;scope/code\&quot; reference. |
| **OmittedApplied** | **int?** | Optional | The number of further applied records omitted from this section, when the valuation changed  more targets than the section carries (large portfolios over long schedules). Null when  nothing was omitted. The market data manifest always carries the complete set. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ScenarioDiagnostics(
    applied: new List<AppliedScenarioShift>(),  // optional — One entry per market data target changed by a shift.
    skipped: ,  // optional — Market data that matched a shift but was skipped (e.g. an element type that does not support  transformation), with the reason. Prefixed with the scenario&#39;s \&quot;scope/code\&quot; reference.
    omittedApplied: 0  // optional — The number of further applied records omitted from this section, when the valuation changed  more targets than the section carries (large portfolios over long schedules). Null when  nothing was omitted. The market data manifest always carries the complete set.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScenarioDiagnostics>(json);
```


## Related Models

- [AppliedScenarioShift](AppliedScenarioShift.md) — used in `Applied`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

