# Finbourne.Sdk.Lusid.Model.StructuredResultDataset

Contains the run-time parameters that are appropriate for check definitions  with datasetSchema.type = \"StructuredResultData\". Names one structured result data document.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveAt** | **DateTimeOffset?** | Optional | The effectiveAt date of the document&#39;s rows to check. Required. |
| **AsAt** | **DateTimeOffset?** | Optional | The asAt date to fetch the data. Nullable. Defaults to latest. |
| **Scope** | **string** | Optional | The scope of the document. Required. |
| **Code** | **string** | Optional | The code of the document. Required. |
| **Source** | **string** | Optional | The platform or vendor that provided the document, e.g. \&quot;Client\&quot;. Required. |
| **ResultType** | **string** | Optional | The document&#39;s result type, e.g. \&quot;UnitResult/Custom\&quot;. Required. |
| **RowSelectorAttribute** | **string** | Optional | A row field to narrow down the rows checked, e.g. rowId[&#39;Instrument/default/LusidInstrumentId&#39;] or  rowData[&#39;Valuation/PV&#39;].Units. Cannot be provided without rowSelectorValue, and vice versa. |
| **RowSelectorValue** | **string** | Optional | The value of the above row field used to narrow down the rows. Cannot be provided without  rowSelectorAttribute, and vice versa. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StructuredResultDataset(
    effectiveAt: DateTimeOffset.Now,  // optional — The effectiveAt date of the document&#39;s rows to check. Required.
    asAt: DateTimeOffset.Now,  // optional — The asAt date to fetch the data. Nullable. Defaults to latest.
    scope: "...",  // optional — The scope of the document. Required.
    code: "...",  // optional — The code of the document. Required.
    source: "...",  // optional — The platform or vendor that provided the document, e.g. \&quot;Client\&quot;. Required.
    resultType: "...",  // optional — The document&#39;s result type, e.g. \&quot;UnitResult/Custom\&quot;. Required.
    rowSelectorAttribute: "...",  // optional — A row field to narrow down the rows checked, e.g. rowId[&#39;Instrument/default/LusidInstrumentId&#39;] or  rowData[&#39;Valuation/PV&#39;].Units. Cannot be provided without rowSelectorValue, and vice versa.
    rowSelectorValue: "..."  // optional — The value of the above row field used to narrow down the rows. Cannot be provided without  rowSelectorAttribute, and vice versa.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StructuredResultDataset>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

