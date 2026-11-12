# Finbourne.Sdk.Lusid.Model.FundTaxScopeExclusions

What the UK chargeable-gains figures leave out of the pooled computation.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentTypes** | **List&lt;string&gt;** | Required | Instrument types that stay on the portfolio&#39;s ordinary accounting method rather than being pooled, by name. |
| **LeafOutcomes** | **List&lt;string&gt;** | Required | Disposal-leg outcomes the configured regime options disapply. Empty under the standard options. |
| **AppliedInFigures** | **bool** | Required | Whether the engine enforces these exclusions when building the pooled lots and gains. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundTaxScopeExclusions(
    instrumentTypes: ,  // required — Instrument types that stay on the portfolio&#39;s ordinary accounting method rather than being pooled, by name.
    leafOutcomes: ,  // required — Disposal-leg outcomes the configured regime options disapply. Empty under the standard options.
    appliedInFigures: true  // required — Whether the engine enforces these exclusions when building the pooled lots and gains.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundTaxScopeExclusions>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

