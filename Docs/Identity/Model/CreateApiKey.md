# Finbourne.Sdk.Identity.Model.CreateApiKey

Create an API key
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The display name for the API key |
| **DeactivationDate** | **DateTimeOffset?** | Optional | The optional date at which the key should deactivate |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new CreateApiKey(
    displayName: "...",  // required — The display name for the API key
    deactivationDate: DateTimeOffset.Now  // optional — The optional date at which the key should deactivate
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateApiKey>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

