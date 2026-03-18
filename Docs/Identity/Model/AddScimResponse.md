# Finbourne.Sdk.Identity.Model.AddScimResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BaseUrl** | **string** | Optional | *No description available.* |
| **ApiToken** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new AddScimResponse(
    baseUrl: "...",  // optional
    apiToken: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AddScimResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

