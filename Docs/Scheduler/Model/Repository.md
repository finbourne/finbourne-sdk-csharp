# Finbourne.Sdk.Scheduler.Model.Repository

An object representation of a repository
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Optional | The identifier of the repository |
| **CreationTime** | **DateTimeOffset** | Optional | Date of  repository creation |
| **LastUpdate** | **DateTimeOffset** | Optional | The last update of the repository |
| **Description** | **string** | Optional | Description of the repository |
| **PullCount** | **long** | Optional | Number of times images were pulled from this repository |
| **ImageCount** | **long** | Optional | The number of versions of this image |
| **Images** | [Link](Link.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new Repository(
    name: "...",  // optional — The identifier of the repository
    creationTime: DateTimeOffset.Now,  // optional — Date of  repository creation
    lastUpdate: DateTimeOffset.Now,  // optional — The last update of the repository
    description: "...",  // optional — Description of the repository
    pullCount: 0L,  // optional — Number of times images were pulled from this repository
    imageCount: 0L,  // optional — The number of versions of this image
    images: new Link(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Repository>(json);
```

- [Link](Link.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

