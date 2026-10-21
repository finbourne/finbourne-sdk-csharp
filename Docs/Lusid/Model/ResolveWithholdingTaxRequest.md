# Finbourne.Sdk.Lusid.Model.ResolveWithholdingTaxRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Mode** | **string** | Required | Where the dimension values come from. Raw: from Dimensions. InstrumentResolved: from the instrument, through the configuration&#39;s value sources, as in booking. Available values: Raw, InstrumentResolved. |
| **TaxCountry** | **string** | Required | The tax country of the holder. It is matched like any other dimension. |
| **ProfileType** | **string** | Required | The profile type of the holder. It is matched like any other dimension. |
| **Dimensions** | **Dictionary&lt;string, string&gt;** | Optional | The value of each matching dimension, keyed by its field name in the rate datasets. A dimension left out is null, as in booking. taxCountry, profileType and ruleSource are not allowed here, and a name that neither dataset matches on is refused. With InstrumentResolved, a value here overrides the derived one, or gives one that the lookup cannot derive (see unresolvedDimensions in the response). |
| **WhtConfig** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **AnomalyDataset** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **MainDataset** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **SourcePriority** | **List&lt;string&gt;** | Optional | Optional. The source priority, most preferred first: it replaces the configuration&#39;s, or is used on its own when there is no configuration. An empty list applies no source filter. |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Optional | The identifiers of the instrument, resolved as for a transaction. Required with InstrumentResolved, not allowed with Raw. |
| **InstrumentScope** | **string** | Optional | Optional. The scope to resolve the instrument in, before the default scope. Only with InstrumentResolved. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ResolveWithholdingTaxRequest(
    mode: "...",  // required — Where the dimension values come from. Raw: from Dimensions. InstrumentResolved: from the instrument, through the configuration&#39;s value sources, as in booking. Available values: Raw, InstrumentResolved.
    taxCountry: "...",  // required — The tax country of the holder. It is matched like any other dimension.
    profileType: "...",  // required — The profile type of the holder. It is matched like any other dimension.
    dimensions: ,  // optional — The value of each matching dimension, keyed by its field name in the rate datasets. A dimension left out is null, as in booking. taxCountry, profileType and ruleSource are not allowed here, and a name that neither dataset matches on is refused. With InstrumentResolved, a value here overrides the derived one, or gives one that the lookup cannot derive (see unresolvedDimensions in the response).
    whtConfig: new ResourceId(...),  // optional
    anomalyDataset: new ResourceId(...),  // optional
    mainDataset: new ResourceId(...),  // optional
    sourcePriority: ,  // optional — Optional. The source priority, most preferred first: it replaces the configuration&#39;s, or is used on its own when there is no configuration. An empty list applies no source filter.
    instrumentIdentifiers: ,  // optional — The identifiers of the instrument, resolved as for a transaction. Required with InstrumentResolved, not allowed with Raw.
    instrumentScope: "..."  // optional — Optional. The scope to resolve the instrument in, before the default scope. Only with InstrumentResolved.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResolveWithholdingTaxRequest>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

