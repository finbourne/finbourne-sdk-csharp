# Finbourne.Sdk.Identity.Model.AuthenticationInformation

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **IssuerUrl** | **string** | Required | *No description available.* |
| **FallbackIssuerUrls** | **List&lt;string&gt;** | Optional | *No description available.* |
| **SamlIdentityProviderId** | **string** | Optional | *No description available.* |
| **Support** | [SupportAccessExpiry](SupportAccessExpiry.md) | Optional | *No description available.* |
| **SupportAccessExpiryWithRole** | [List&lt;SupportAccessExpiryWithRole&gt;](SupportAccessExpiryWithRole.md) | Optional | *No description available.* |
| **Status** | **bool** | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new AuthenticationInformation(
    issuerUrl: "...",  // required
    fallbackIssuerUrls: ,  // optional
    samlIdentityProviderId: "...",  // optional
    support: new SupportAccessExpiry(...),  // optional
    supportAccessExpiryWithRole: new List<SupportAccessExpiryWithRole>(),  // optional
    status: true,  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AuthenticationInformation>(json);
```

- [SupportAccessExpiry](SupportAccessExpiry.md)
- [SupportAccessExpiryWithRole](SupportAccessExpiryWithRole.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

