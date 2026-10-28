# Finbourne.Sdk.Luminesce.Model.CustomMultiQueryExport

Where (and how) to save the results of a custom multi-query to Drive, as one file, once its queries are done: the same as calling `api/MultiQueryBackground/{executionId}/drive` then, which may still be called as often as wanted.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DriveLocationAndFileName** | **string** | Optional | Location and file name within Drive to save to. Missing paths will be created, and extension (if given) will be ignored and inferred from the format (zip where several results are zipped). May contain the placeholders &#x60;{executionId}&#x60;, &#x60;{date:format}&#x60; (when the queries started, UTC, e.g. &#x60;{date:yyyyMMdd}&#x60;) and &#x60;{param:name}&#x60; (the value of a scalar parameter). |
| **Format** | **ExportType** | Optional | *No description available.* |
| **MayOverwrite** | **bool?** | Optional | If there is an existing file at the location with the same name should it be overwritten (rather than the export failing)?  False by default. |
| **DriveTemplateLocation** | **string** | Optional | Drive path and full file name including extension of a template to export with.  Only Excel and Pdf exports support templates. |
| **DateTimeFormat** | **string** | Optional | Format to apply for DateTime data, leaving blank gives the Luminesce Exporter default, currently &#x60;yyyy-MM-dd HH:mm:ss.fff&#x60; |
| **WhenSomeFail** | **bool?** | Optional | Should the results of the queries that succeeded still be saved when others did not?  False by default, meaning nothing is saved then. Either way the multi-query as a whole is reported as failed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new CustomMultiQueryExport(
    driveLocationAndFileName: "...",  // optional — Location and file name within Drive to save to. Missing paths will be created, and extension (if given) will be ignored and inferred from the format (zip where several results are zipped). May contain the placeholders &#x60;{executionId}&#x60;, &#x60;{date:format}&#x60; (when the queries started, UTC, e.g. &#x60;{date:yyyyMMdd}&#x60;) and &#x60;{param:name}&#x60; (the value of a scalar parameter).
    format: ,  // optional
    mayOverwrite: true,  // optional — If there is an existing file at the location with the same name should it be overwritten (rather than the export failing)?  False by default.
    driveTemplateLocation: "...",  // optional — Drive path and full file name including extension of a template to export with.  Only Excel and Pdf exports support templates.
    dateTimeFormat: "...",  // optional — Format to apply for DateTime data, leaving blank gives the Luminesce Exporter default, currently &#x60;yyyy-MM-dd HH:mm:ss.fff&#x60;
    whenSomeFail: true  // optional — Should the results of the queries that succeeded still be saved when others did not?  False by default, meaning nothing is saved then. Either way the multi-query as a whole is reported as failed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustomMultiQueryExport>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

