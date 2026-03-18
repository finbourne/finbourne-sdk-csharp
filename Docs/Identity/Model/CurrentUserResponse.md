# Finbourne.Sdk.Identity.Model.CurrentUserResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | The user&#39;s system supplied unique identifier |
| **EmailAddress** | **string** | Required | The user&#39;s email address which may be null depending on the authentication method |
| **Type** | **string** | Required | The type of user (e.g. Personal or Service) |
| **DomainType** | **string** | Optional | The type of domain in which the user exists |
| **UserExpiry** | **DateTimeOffset?** | Optional | The user&#39;s user expiry datetime |
| **Groups** | **List&lt;string&gt;** | Optional | The groups this user belongs to |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new CurrentUserResponse(
    id: "...",  // required — The user&#39;s system supplied unique identifier
    emailAddress: "...",  // required — The user&#39;s email address which may be null depending on the authentication method
    type: "...",  // required — The type of user (e.g. Personal or Service)
    domainType: "...",  // optional — The type of domain in which the user exists
    userExpiry: DateTimeOffset.Now,  // optional — The user&#39;s user expiry datetime
    groups: ,  // optional — The groups this user belongs to
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CurrentUserResponse>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

