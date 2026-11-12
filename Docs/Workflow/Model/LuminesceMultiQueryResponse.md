# Finbourne.Sdk.Workflow.Model.LuminesceMultiQueryResponse

Readonly configuration for the Luminesce custom multi-query Worker
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | The type of worker |
| **WorkspaceKey** | **string** | Optional | The Workspaces key of the multi-query the worker runs |
| **DriveLocationAndFileName** | **string** | Optional | Where in Drive the results are saved, which may contain placeholders |
| **Format** | **string** | Optional | The format the results are saved in, csv when not given |
| **MayOverwrite** | **bool?** | Optional | Whether an existing file of the same name may be overwritten |
| **DriveTemplateLocation** | **string** | Optional | The Drive path of the template the results are saved with |
| **DateTimeFormat** | **string** | Optional | The format DateTime values are written in |
| **WhenSomeFail** | **bool?** | Optional | Whether the results of the queries that succeeded are still saved when others did not |
| **KeepForSeconds** | **int** | Optional | How long Luminesce keeps the results once done, in seconds |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new LuminesceMultiQueryResponse(
    type: "...",  // optional — The type of worker
    workspaceKey: "...",  // optional — The Workspaces key of the multi-query the worker runs
    driveLocationAndFileName: "...",  // optional — Where in Drive the results are saved, which may contain placeholders
    format: "...",  // optional — The format the results are saved in, csv when not given
    mayOverwrite: true,  // optional — Whether an existing file of the same name may be overwritten
    driveTemplateLocation: "...",  // optional — The Drive path of the template the results are saved with
    dateTimeFormat: "...",  // optional — The format DateTime values are written in
    whenSomeFail: true,  // optional — Whether the results of the queries that succeeded are still saved when others did not
    keepForSeconds: 0  // optional — How long Luminesce keeps the results once done, in seconds
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LuminesceMultiQueryResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

