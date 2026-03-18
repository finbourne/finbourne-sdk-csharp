# Finbourne.Sdk.Lusid.Model.StructuredResultDataId

An identifier that uniquely describes an item of structured result data such as the risk to an interest curve or a set of yields or analytics on an index.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Source** | **string** | Required | The platform or vendor that provided the structured result data, e.g. &#39;client&#39;. This is primarily of interest when data could have been sourced from multiple sources |
| **Code** | **string** | Optional | The identifier for the entity that this id describes. It could be an index, instrument or other form of structured data |
| **EffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The effectiveAt or cut label that this item of structured result data is/was updated/inserted with. |
| **ResultType** | **string** | Optional | An identifier that denotes the class of data that the id points to. This is not the same as the format, but a more generic identifier such as &#39;risk result&#39;, &#39;cashflow&#39;, &#39;index&#39; or similar. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StructuredResultDataId(
    source: "...",  // required — The platform or vendor that provided the structured result data, e.g. &#39;client&#39;. This is primarily of interest when data could have been sourced from multiple sources
    code: "...",  // optional — The identifier for the entity that this id describes. It could be an index, instrument or other form of structured data
    effectiveAt: new DateTimeOrCutLabel(...),  // optional — The effectiveAt or cut label that this item of structured result data is/was updated/inserted with.
    resultType: "..."  // optional — An identifier that denotes the class of data that the id points to. This is not the same as the format, but a more generic identifier such as &#39;risk result&#39;, &#39;cashflow&#39;, &#39;index&#39; or similar.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StructuredResultDataId>(json);
```

- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveAt`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

