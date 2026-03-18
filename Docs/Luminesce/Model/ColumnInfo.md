# Finbourne.Sdk.Luminesce.Model.ColumnInfo

Information on how to construct a file-read sql query
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Select** | **bool** | Optional | Should the column be used/selected? |
| **Type** | **DataType** | Optional | *No description available.* |
| **Name** | **string** | Optional | The name of the column |
| **XPath** | **string** | Optional | Xpath for the column (only applicable to XML defined columns) |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ColumnInfo(
    select: true,  // optional — Should the column be used/selected?
    type: ,  // optional
    name: "...",  // optional — The name of the column
    xPath: "..."  // optional — Xpath for the column (only applicable to XML defined columns)
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ColumnInfo>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

