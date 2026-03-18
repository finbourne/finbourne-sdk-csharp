# Finbourne.Sdk.Scheduler.Model.Tag

Represents data of an image's tag
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Optional | The name of the tag |
| **PullTime** | **DateTimeOffset** | Optional | The latest pull time |
| **PushTime** | **DateTimeOffset** | Optional | The date of the tag&#39;s push |
| **Signed** | **bool** | Optional | Indicates whether the tag is signed |
| **Immutable** | **bool** | Optional | Indicates whether the tag is immutable |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new Tag(
    name: "...",  // optional — The name of the tag
    pullTime: DateTimeOffset.Now,  // optional — The latest pull time
    pushTime: DateTimeOffset.Now,  // optional — The date of the tag&#39;s push
    signed: true,  // optional — Indicates whether the tag is signed
    immutable: true  // optional — Indicates whether the tag is immutable
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Tag>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

