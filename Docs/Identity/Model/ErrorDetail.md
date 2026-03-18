# Finbourne.Sdk.Identity.Model.ErrorDetail

Provides details about an entity error that occured
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Optional | Id of the entity this error relates to |
| **Type** | **string** | Optional | Error type |
| **Detail** | **string** | Optional | Human readable description of the error |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new ErrorDetail(
    id: "...",  // optional — Id of the entity this error relates to
    type: "...",  // optional — Error type
    detail: "..."  // optional — Human readable description of the error
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ErrorDetail>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

