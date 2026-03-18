# Finbourne.Sdk.Drive.Model.CreateFolder

DTO representing the creation of a folder
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Path** | **string** | Required | Path of the created folder |
| **Name** | **string** | Required | Name of the created folder |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Drive.Model;

var instance = new CreateFolder(
    path: "...",  // required — Path of the created folder
    name: "..."  // required — Name of the created folder
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateFolder>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

