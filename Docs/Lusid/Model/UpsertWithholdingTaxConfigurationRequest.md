# Finbourne.Sdk.Lusid.Model.UpsertWithholdingTaxConfigurationRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AnomalyDataset** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **MainDataset** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **SourcePriority** | **List&lt;string&gt;** | Optional | The rule sources in priority order, most preferred first. Optional: a single-source customer configures none and leaves ruleSource blank on every rate row, in which case no source filter is applied and specificity alone decides. |
| **ValueSources** | [List&lt;WithholdingTaxValueSource&gt;](WithholdingTaxValueSource.md) | Optional | One declaration per customer-defined matching dimension across both datasets, naming where the engine reads that dimension&#39;s value from. A dataset column name cannot imply a storage location, so a declaration is required for every customer dimension: an unmapped dimension is never supplied by the matching request, so no row ever matches on it and the customer silently gets a broader rate than they configured. No declaration is required for taxCountry or profileType, which the engine fills from the waterfall, nor for ruleSource, which is compared against SourcePriority. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertWithholdingTaxConfigurationRequest(
    anomalyDataset: new ResourceId(...),  // required
    mainDataset: new ResourceId(...),  // required
    sourcePriority: ,  // optional — The rule sources in priority order, most preferred first. Optional: a single-source customer configures none and leaves ruleSource blank on every rate row, in which case no source filter is applied and specificity alone decides.
    valueSources: new List<WithholdingTaxValueSource>()  // optional — One declaration per customer-defined matching dimension across both datasets, naming where the engine reads that dimension&#39;s value from. A dataset column name cannot imply a storage location, so a declaration is required for every customer dimension: an unmapped dimension is never supplied by the matching request, so no row ever matches on it and the customer silently gets a broader rate than they configured. No declaration is required for taxCountry or profileType, which the engine fills from the waterfall, nor for ruleSource, which is compared against SourcePriority.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertWithholdingTaxConfigurationRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [WithholdingTaxValueSource](WithholdingTaxValueSource.md) — used in `ValueSources`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

