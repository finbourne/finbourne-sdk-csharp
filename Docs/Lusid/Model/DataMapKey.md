# Finbourne.Sdk.Lusid.Model.DataMapKey

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VarVersion** | **string** | Optional | The version of the mappings. It is possible that a client will wish to update mappings over time. The version identifies the MAJOR.MINOR.PATCH version  of the mappings that the client assigns it. |
| **Code** | **string** | Optional | A unique name to semantically identify the mapping set. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DataMapKey(
    varVersion: "...",  // optional — The version of the mappings. It is possible that a client will wish to update mappings over time. The version identifies the MAJOR.MINOR.PATCH version  of the mappings that the client assigns it.
    code: "..."  // optional — A unique name to semantically identify the mapping set.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DataMapKey>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

