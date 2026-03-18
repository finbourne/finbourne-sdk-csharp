# Finbourne.Sdk.Scheduler.Model.UploadImageInstructions

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DockerLoginCommand** | **string** | Required | *No description available.* |
| **BuildVersionedDockerImageCommand** | **string** | Required | *No description available.* |
| **TagVersionedDockerImageCommand** | **string** | Required | *No description available.* |
| **PushVersionedDockerImageCommand** | **string** | Required | *No description available.* |
| **TagLatestDockerImageCommand** | **string** | Optional | *No description available.* |
| **PushLatestDockerImageCommand** | **string** | Optional | *No description available.* |
| **ExpiryTime** | **DateTimeOffset?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new UploadImageInstructions(
    dockerLoginCommand: "...",  // required
    buildVersionedDockerImageCommand: "...",  // required
    tagVersionedDockerImageCommand: "...",  // required
    pushVersionedDockerImageCommand: "...",  // required
    tagLatestDockerImageCommand: "...",  // optional
    pushLatestDockerImageCommand: "...",  // optional
    expiryTime: DateTimeOffset.Now  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UploadImageInstructions>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

