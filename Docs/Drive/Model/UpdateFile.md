# Finbourne.Sdk.Drive.Model.UpdateFile

DTO representing the update of the name or path of a file
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Path** | **string** | Required | Path of the updated file |
| **Name** | **string** | Required | Name of the updated file |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Drive.Model;

var instance = new UpdateFile(
    path: "...",  // required — Path of the updated file
    name: "..."  // required — Name of the updated file
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateFile>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

