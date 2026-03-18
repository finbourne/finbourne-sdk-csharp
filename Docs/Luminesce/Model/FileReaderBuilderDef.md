# Finbourne.Sdk.Luminesce.Model.FileReaderBuilderDef

Information on how to construct a file-read sql query
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AutoDetect** | **AutoDetectType** | Optional | *No description available.* |
| **Columns** | [List&lt;ColumnInfo&gt;](ColumnInfo.md) | Optional | Column information for the results |
| **Limit** | **int** | Optional | What limit be added to the load query?  Less than or equal to zero means none |
| **Source** | [Source](Source.md) | Optional | *No description available.* |
| **AvailableSources** | [List&lt;Source&gt;](Source.md) | Optional | The source locations the user has access to.  The provider in essence. |
| **VariableName** | **string** | Optional | The name of the variable for the &#x60;use&#x60; statement |
| **FilePath** | **string** | Optional | The file (or folder) path |
| **FolderFilter** | **string** | Optional | The filter to apply to a folder (all matching files then being read) a RegExp |
| **ZipFilter** | **string** | Optional | The filter to apply to folder structures with zip archives (all matching files then being read) a RegExp |
| **AddFileName** | **bool** | Optional | Should a file name column be added to the output? |
| **Csv** | [OptionsCsv](OptionsCsv.md) | Optional | *No description available.* |
| **Excel** | [OptionsExcel](OptionsExcel.md) | Optional | *No description available.* |
| **SqLite** | [OptionsSqLite](OptionsSqLite.md) | Optional | *No description available.* |
| **Xml** | [OptionsXml](OptionsXml.md) | Optional | *No description available.* |
| **Parquet** | [OptionsParquet](OptionsParquet.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new FileReaderBuilderDef(
    autoDetect: ,  // optional
    columns: new List<ColumnInfo>(),  // optional — Column information for the results
    limit: 0,  // optional — What limit be added to the load query?  Less than or equal to zero means none
    source: new Source(...),  // optional
    availableSources: new List<Source>(),  // optional — The source locations the user has access to.  The provider in essence.
    variableName: "...",  // optional — The name of the variable for the &#x60;use&#x60; statement
    filePath: "...",  // optional — The file (or folder) path
    folderFilter: "...",  // optional — The filter to apply to a folder (all matching files then being read) a RegExp
    zipFilter: "...",  // optional — The filter to apply to folder structures with zip archives (all matching files then being read) a RegExp
    addFileName: true,  // optional — Should a file name column be added to the output?
    csv: new OptionsCsv(...),  // optional
    excel: new OptionsExcel(...),  // optional
    sqLite: new OptionsSqLite(...),  // optional
    xml: new OptionsXml(...),  // optional
    parquet: new OptionsParquet(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FileReaderBuilderDef>(json);
```

- [ColumnInfo](ColumnInfo.md) — used in `Columns`
- [Source](Source.md)
- [Source](Source.md) — used in `AvailableSources`
- [OptionsCsv](OptionsCsv.md)
- [OptionsExcel](OptionsExcel.md)
- [OptionsSqLite](OptionsSqLite.md)
- [OptionsXml](OptionsXml.md)
- [OptionsParquet](OptionsParquet.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

