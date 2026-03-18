# Finbourne.Sdk.Identity.Model.OAuthApplication

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | *No description available.* |
| **Type** | **string** | Required | *No description available.* |
| **DisplayName** | **string** | Required | *No description available.* |
| **Secret** | **string** | Optional | *No description available.* |
| **ClientId** | **string** | Required | *No description available.* |
| **Issuer** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new OAuthApplication(
    id: "...",  // required
    type: "...",  // required
    displayName: "...",  // required
    secret: "...",  // optional
    clientId: "...",  // required
    issuer: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OAuthApplication>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

