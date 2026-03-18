# Finbourne.Sdk.Lusid.Model.ScriptMapReference

Provides information about the location of a script map within the configuration store
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope of the configuration store entry where the translation map is located. |
| **Code** | **string** | Required | The code of the configuration store entry where the translation map is located. |
| **Key** | **string** | Required | The key of the configuration store entry where the translation map is located. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ScriptMapReference(
    scope: "...",  // required — The scope of the configuration store entry where the translation map is located.
    code: "...",  // required — The code of the configuration store entry where the translation map is located.
    key: "..."  // required — The key of the configuration store entry where the translation map is located.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScriptMapReference>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

