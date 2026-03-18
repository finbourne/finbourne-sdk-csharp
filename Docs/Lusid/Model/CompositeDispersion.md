# Finbourne.Sdk.Lusid.Model.CompositeDispersion

A list of Dispersion calculations for the given years.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveAt** | **DateTimeOffset** | Required | The date for which dipsersion calculation has been done. This should be 31 Dec for each given year. |
| **DispersionCalculation** | **decimal?** | Optional | The result for the dispersion calculation on the given effectiveAt. |
| **Variance** | **decimal?** | Optional | The variance on the given effectiveAt. |
| **FirstQuartile** | **decimal?** | Optional | First Quartile (Q1) &#x3D;  (lower quartile) &#x3D; the middle of the bottom half of the returns. |
| **ThirdQuartile** | **decimal?** | Optional | Third Quartile (Q3) &#x3D;  (higher quartile) &#x3D; the middle of the top half of the returns. |
| **Range** | **decimal?** | Optional | Highest return - Lowest return. |
| **ConstituentsInScope** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | List containing Composite members which are part of the dispersion calcualtion. |
| **ConstituentsExcluded** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | List containing the Composite members which are not part of the dispersion calculation |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CompositeDispersion(
    effectiveAt: DateTimeOffset.Now,  // required — The date for which dipsersion calculation has been done. This should be 31 Dec for each given year.
    dispersionCalculation: 0.0d,  // optional — The result for the dispersion calculation on the given effectiveAt.
    variance: 0.0d,  // optional — The variance on the given effectiveAt.
    firstQuartile: 0.0d,  // optional — First Quartile (Q1) &#x3D;  (lower quartile) &#x3D; the middle of the bottom half of the returns.
    thirdQuartile: 0.0d,  // optional — Third Quartile (Q3) &#x3D;  (higher quartile) &#x3D; the middle of the top half of the returns.
    range: 0.0d,  // optional — Highest return - Lowest return.
    constituentsInScope: new List<ResourceId>(),  // optional — List containing Composite members which are part of the dispersion calcualtion.
    constituentsExcluded: new List<ResourceId>()  // optional — List containing the Composite members which are not part of the dispersion calculation
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CompositeDispersion>(json);
```

- [ResourceId](ResourceId.md) — used in `ConstituentsInScope`
- [ResourceId](ResourceId.md) — used in `ConstituentsExcluded`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

