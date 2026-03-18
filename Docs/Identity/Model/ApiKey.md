# Finbourne.Sdk.Identity.Model.ApiKey

The metadata of an API key
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | The unique Id of the API key |
| **DisplayName** | **string** | Required | The display name of the API key |
| **CreatedDate** | **DateTimeOffset** | Required | The creation date of the API key |
| **DeactivationDate** | **DateTimeOffset?** | Optional | The deactivation date of the API key |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new ApiKey(
    id: "...",  // required — The unique Id of the API key
    displayName: "...",  // required — The display name of the API key
    createdDate: DateTimeOffset.Now,  // required — The creation date of the API key
    deactivationDate: DateTimeOffset.Now  // optional — The deactivation date of the API key
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ApiKey>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

