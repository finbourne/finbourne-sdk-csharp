# Finbourne.Sdk.Luminesce.Model.ExportDateFormat

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Preset** | **string** | Optional | *No description available.* |
| **Pattern** | **string** | Optional | *No description available.* |
| **ExcelFormat** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ExportDateFormat(
    preset: "...",  // optional
    pattern: "...",  // optional
    excelFormat: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExportDateFormat>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

