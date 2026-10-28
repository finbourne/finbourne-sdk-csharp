# Finbourne.Sdk.Luminesce.Model.MultiQueryExportState

What became of the export of a custom multi-query once its queries were done (persisted in its shared state, so known to every pod).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DriveLocationAndFileName** | **string** | Optional | Where it was to be saved, its placeholders filled in |
| **SavedTo** | **string** | Optional | The Drive path (and file name, with its extension) it was saved to, once it has been |
| **Error** | **string** | Optional | Why it was not saved, if it was not |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new MultiQueryExportState(
    driveLocationAndFileName: "...",  // optional — Where it was to be saved, its placeholders filled in
    savedTo: "...",  // optional — The Drive path (and file name, with its extension) it was saved to, once it has been
    error: "..."  // optional — Why it was not saved, if it was not
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MultiQueryExportState>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

