# Finbourne.Sdk.Scheduler.Model.ImageSummary

Represents the metadata of an image
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Optional | Name of the image |
| **PushTime** | **DateTimeOffset?** | Optional | The push time of the image |
| **PullTime** | **DateTimeOffset?** | Optional | The latest pull time of the image |
| **Digest** | **string** | Optional | The digest of the image |
| **Size** | **long?** | Optional | The size of the image (in bytes) |
| **Tags** | [List&lt;Tag&gt;](Tag.md) | Optional | The tags of the image |
| **ScanStatus** | **string** | Optional | The Scan Status of the stated image |
| **ScanSummary** | [ScanSummary](ScanSummary.md) | Optional | *No description available.* |
| **Link** | [Link](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new ImageSummary(
    name: "...",  // optional — Name of the image
    pushTime: DateTimeOffset.Now,  // optional — The push time of the image
    pullTime: DateTimeOffset.Now,  // optional — The latest pull time of the image
    digest: "...",  // optional — The digest of the image
    size: 0L,  // optional — The size of the image (in bytes)
    tags: new List<Tag>(),  // optional — The tags of the image
    scanStatus: "...",  // optional — The Scan Status of the stated image
    scanSummary: new ScanSummary(...),  // optional
    link: new Link(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ImageSummary>(json);
```

- [Tag](Tag.md) — used in `Tags`
- [ScanSummary](ScanSummary.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

