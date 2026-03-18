# Finbourne.Sdk.Drive.Model.UpdateFolder

DTO representing the update of the name or path of a file
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Path** | **string** | Required | Path of the updated folder |
| **Name** | **string** | Required | Name of the updated folder |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Drive.Model;

var instance = new UpdateFolder(
    path: "...",  // required — Path of the updated folder
    name: "..."  // required — Name of the updated folder
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateFolder>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

