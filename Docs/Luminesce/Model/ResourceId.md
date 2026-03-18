# Finbourne.Sdk.Luminesce.Model.ResourceId

Unique identifier for a resource
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope used to identify a resource |
| **Code** | **string** | Optional | The code used to identify a resource |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ResourceId(
    scope: "...",  // required — The scope used to identify a resource
    code: "..."  // optional — The code used to identify a resource
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResourceId>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

