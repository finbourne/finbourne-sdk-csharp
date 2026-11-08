# Finbourne.Sdk.Luminesce.Model.ExportFormatting

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Timezone** | **string** | Optional | *No description available.* |
| **Locale** | **string** | Optional | *No description available.* |
| **Tables** | [List&lt;TableExport&gt;](TableExport.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ExportFormatting(
    timezone: "...",  // optional
    locale: "...",  // optional
    tables: new List<TableExport>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExportFormatting>(json);
```

- [TableExport](TableExport.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

