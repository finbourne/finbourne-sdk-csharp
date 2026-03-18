# Finbourne.Sdk.Drive.Model.SearchBody

DTO representing the search query
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **WithPath** | **string** | Optional | Optional path field to limit the search to result with a matching (case insensitive) path |
| **Name** | **string** | Required | Name of the file or folder to be searched |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Drive.Model;

var instance = new SearchBody(
    withPath: "...",  // optional — Optional path field to limit the search to result with a matching (case insensitive) path
    name: "..."  // required — Name of the file or folder to be searched
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SearchBody>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

