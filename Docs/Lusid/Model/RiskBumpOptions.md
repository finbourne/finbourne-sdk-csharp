# Finbourne.Sdk.Lusid.Model.RiskBumpOptions

Per-recipe configuration of the bump sizes used by the finite-difference Risk/_* measures.  Results are always reported per ResultSensitivity regardless of the shift used to compute  them: the calculators divide by shift/resultSensitivity, so choosing a wider shift (e.g.  10bp for a market element with coarse quote precision) changes the estimator, not the unit.  Every member is optional and an absent member keeps the historical default.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DeltaShift** | **decimal?** | Optional | The shift applied for delta/gamma bumps on any asset type without an explicit override.  Must be strictly positive. Defaults to 0.0001 (1bp) when not supplied. |
| **ResultSensitivity** | **decimal?** | Optional | The move the reported sensitivity is normalised to. Must be strictly positive.  Defaults to 0.0001 (results per 1bp move) when not supplied. |
| **DeltaShiftOverrides** | **Dictionary&lt;string, decimal&gt;** | Optional | Per-asset-type overrides of the delta shift, keyed by asset type (e.g. \&quot;Rates\&quot;, \&quot;Credit\&quot;,  \&quot;Fx\&quot;). Values must be strictly positive. Asset types without an override use DeltaShift. |
| **LadderShiftOverrides** | **Dictionary&lt;string, List&lt;decimal&gt;&gt;** | Optional | Per-asset-type overrides of the shift grid used by ladder measures, keyed by asset type  (e.g. \&quot;Rates\&quot;, \&quot;Fx\&quot;). Each grid must be non-empty and strictly increasing; zero is a  legitimate rung, as the default grids include the base scenario. Asset types without an  override use the standard grids. |
| **ParityRelativeTolerance** | **decimal?** | Optional | The relative tolerance for RiskEngine \&quot;Parity\&quot; checks, applied as  |bump - adjoint| &lt;&#x3D; max(absolute floor, |bump| * tolerance). Defaults to 0.001. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RiskBumpOptions(
    deltaShift: 0.0d,  // optional — The shift applied for delta/gamma bumps on any asset type without an explicit override.  Must be strictly positive. Defaults to 0.0001 (1bp) when not supplied.
    resultSensitivity: 0.0d,  // optional — The move the reported sensitivity is normalised to. Must be strictly positive.  Defaults to 0.0001 (results per 1bp move) when not supplied.
    deltaShiftOverrides: ,  // optional — Per-asset-type overrides of the delta shift, keyed by asset type (e.g. \&quot;Rates\&quot;, \&quot;Credit\&quot;,  \&quot;Fx\&quot;). Values must be strictly positive. Asset types without an override use DeltaShift.
    ladderShiftOverrides: ,  // optional — Per-asset-type overrides of the shift grid used by ladder measures, keyed by asset type  (e.g. \&quot;Rates\&quot;, \&quot;Fx\&quot;). Each grid must be non-empty and strictly increasing; zero is a  legitimate rung, as the default grids include the base scenario. Asset types without an  override use the standard grids.
    parityRelativeTolerance: 0.0d  // optional — The relative tolerance for RiskEngine \&quot;Parity\&quot; checks, applied as  |bump - adjoint| &lt;&#x3D; max(absolute floor, |bump| * tolerance). Defaults to 0.001.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RiskBumpOptions>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

