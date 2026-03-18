# Finbourne.Sdk.Luminesce.Model.OptionsParquet

Additional options applicable to the given SourceType
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ColumnNamesWanted** | **string** | Optional | Column (by Name) that should be returned (comma delimited list) |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new OptionsParquet(
    columnNamesWanted: "..."  // optional — Column (by Name) that should be returned (comma delimited list)
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OptionsParquet>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

