# Finbourne.Sdk.Horizon.Model.FileDetails

Information associated with files
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FileName** | **string** | Required | *No description available.* |
| **FileType** | **string** | Optional | *No description available.* |
| **Id** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new FileDetails(
    fileName: "...",  // required
    fileType: "...",  // optional
    id: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FileDetails>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

