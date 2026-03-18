# Finbourne.Sdk.Scheduler.Model.UploadImageRequest

Request to upload image for Scheduler use
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ImageName** | **string** | Required | Name of the image to be uploaded |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new UploadImageRequest(
    imageName: "..."  // required — Name of the image to be uploaded
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UploadImageRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

