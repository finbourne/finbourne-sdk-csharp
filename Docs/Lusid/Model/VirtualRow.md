# Finbourne.Sdk.Lusid.Model.VirtualRow

Rows identified by the composite id, based on the data maps
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RowId** | **Dictionary&lt;string, string&gt;** | Optional | The identifier for the row. This is keyed by address keys, and values obtained through applying the data map to the documents. |
| **RowData** | [Dictionary&lt;string, ResultValue&gt;](ResultValue.md) | Optional | The data for the particular row |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new VirtualRow(
    rowId: ,  // optional — The identifier for the row. This is keyed by address keys, and values obtained through applying the data map to the documents.
    rowData: new ResultValue(...)  // optional — The data for the particular row
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VirtualRow>(json);
```

- [ResultValue](ResultValue.md) — used in `RowData`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

