# Finbourne.Sdk.Luminesce.Model.OptionsSqLite

Additional options applicable to the given SourceType
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Table** | **string** | Optional | Table name to read.  If missing then an error will be raised if there is any number of tables other than one. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new OptionsSqLite(
    table: "..."  // optional — Table name to read.  If missing then an error will be raised if there is any number of tables other than one.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OptionsSqLite>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

