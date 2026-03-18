# Finbourne.Sdk.Lusid.Model.FileResponse

Allows a file (represented as a stream) to be returned from an Api call
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FileStream** | **System.IO.Stream** | Optional | *No description available.* |
| **ContentType** | **string** | Optional | *No description available.* |
| **DownloadedFilename** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FileResponse(
    fileStream: ,  // optional
    contentType: "...",  // optional
    downloadedFilename: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FileResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

