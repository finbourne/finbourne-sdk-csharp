# Finbourne.Sdk.Identity.Model.UserResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | The user&#39;s system supplied unique identifier |
| **AlternativeUserIds** | **Dictionary&lt;string, string&gt;** | Optional | The user&#39;s alternative IDs |
| **EmailAddress** | **string** | Required | The user&#39;s emailAddress address, which must be unique within the system |
| **SecondEmailAddress** | **string** | Optional | The user&#39;s second email address. Only allowed for service users. |
| **Login** | **string** | Required | *No description available.* |
| **FirstName** | **string** | Required | The user&#39;s first name |
| **LastName** | **string** | Required | The user&#39;s last name |
| **Roles** | [List&lt;RoleResponse&gt;](RoleResponse.md) | Optional | The roles that the user has. |
| **Type** | **string** | Required | The type of user (e.g. Personal or Service) |
| **Status** | **string** | Required | The status of the user |
| **External** | **bool** | Required | Whether or not the user originates from an external identity system |
| **LastLogin** | **DateTimeOffset?** | Optional | Last time the user logged in |
| **LastUpdated** | **DateTimeOffset?** | Optional | Last time the user was updated |
| **Created** | **DateTimeOffset?** | Optional | Date the user was created |
| **PasswordChanged** | **DateTimeOffset?** | Optional | Last time the password was changed for this user |
| **UserExpiry** | **DateTimeOffset?** | Optional | The user&#39;s expiry unix datetime |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new UserResponse(
    id: "...",  // required — The user&#39;s system supplied unique identifier
    alternativeUserIds: ,  // optional — The user&#39;s alternative IDs
    emailAddress: "...",  // required — The user&#39;s emailAddress address, which must be unique within the system
    secondEmailAddress: "...",  // optional — The user&#39;s second email address. Only allowed for service users.
    login: "...",  // required
    firstName: "...",  // required — The user&#39;s first name
    lastName: "...",  // required — The user&#39;s last name
    roles: new List<RoleResponse>(),  // optional — The roles that the user has.
    type: "...",  // required — The type of user (e.g. Personal or Service)
    status: "...",  // required — The status of the user
    external: true,  // required — Whether or not the user originates from an external identity system
    lastLogin: DateTimeOffset.Now,  // optional — Last time the user logged in
    lastUpdated: DateTimeOffset.Now,  // optional — Last time the user was updated
    created: DateTimeOffset.Now,  // optional — Date the user was created
    passwordChanged: DateTimeOffset.Now,  // optional — Last time the password was changed for this user
    userExpiry: DateTimeOffset.Now,  // optional — The user&#39;s expiry unix datetime
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UserResponse>(json);
```

- [RoleResponse](RoleResponse.md) — used in `Roles`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

