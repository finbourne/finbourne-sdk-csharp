# Finbourne.Sdk.Identity.Model.ClaimMappings

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **UserId** | **string** | Required | *No description available.* |
| **Login** | **string** | Required | *No description available.* |
| **Email** | **string** | Required | *No description available.* |
| **FirstName** | **string** | Required | *No description available.* |
| **LastName** | **string** | Required | *No description available.* |
| **UserType** | **string** | Required | *No description available.* |
| **Groups** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new ClaimMappings(
    userId: "...",  // required
    login: "...",  // required
    email: "...",  // required
    firstName: "...",  // required
    lastName: "...",  // required
    userType: "...",  // required
    groups: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ClaimMappings>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

