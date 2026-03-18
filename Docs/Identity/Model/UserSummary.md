# Finbourne.Sdk.Identity.Model.UserSummary

Lightweight view of an user details
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Optional | The user id |
| **Login** | **string** | Optional | The user login |
| **Email** | **string** | Optional | The email address registered for that user |
| **SecondEmail** | **string** | Optional | *No description available.* |
| **FirstName** | **string** | Optional | User&#39;s first name |
| **LastName** | **string** | Optional | User&#39;s last name |
| **Type** | **string** | Optional | User&#39;s type (Personal, Service...) |
| **AlternativeUserIds** | **Dictionary&lt;string, string&gt;** | Optional | User&#39;s alternative user IDs. Only returned for the current user |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new UserSummary(
    id: "...",  // optional — The user id
    login: "...",  // optional — The user login
    email: "...",  // optional — The email address registered for that user
    secondEmail: "...",  // optional
    firstName: "...",  // optional — User&#39;s first name
    lastName: "...",  // optional — User&#39;s last name
    type: "...",  // optional — User&#39;s type (Personal, Service...)
    alternativeUserIds: ,  // optional — User&#39;s alternative user IDs. Only returned for the current user
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UserSummary>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

