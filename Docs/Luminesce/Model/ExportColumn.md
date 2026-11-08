# Finbourne.Sdk.Luminesce.Model.ExportColumn

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ColId** | **string** | Required | *No description available.* |
| **Header** | **string** | Optional | *No description available.* |
| **DataType** | **ExportColumnDataType** | Optional | *No description available.* |
| **Hidden** | **bool** | Optional | *No description available.* |
| **WrapText** | **bool** | Optional | *No description available.* |
| **ColumnColor** | [ExportColumnColor](ExportColumnColor.md) | Optional | *No description available.* |
| **Number** | [ExportNumberFormat](ExportNumberFormat.md) | Optional | *No description available.* |
| **Date** | [ExportDateFormat](ExportDateFormat.md) | Optional | *No description available.* |
| **ConditionalRules** | [List&lt;ExportConditionalRule&gt;](ExportConditionalRule.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ExportColumn(
    colId: "...",  // required
    header: "...",  // optional
    dataType: ,  // optional
    hidden: true,  // optional
    wrapText: true,  // optional
    columnColor: new ExportColumnColor(...),  // optional
    number: new ExportNumberFormat(...),  // optional
    date: new ExportDateFormat(...),  // optional
    conditionalRules: new List<ExportConditionalRule>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExportColumn>(json);
```

- [ExportColumnColor](ExportColumnColor.md)
- [ExportNumberFormat](ExportNumberFormat.md)
- [ExportDateFormat](ExportDateFormat.md)
- [ExportConditionalRule](ExportConditionalRule.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

