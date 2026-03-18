# Finbourne.Sdk.Identity.Model.CreateUserRequest

Details necessary for creating a new user
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FirstName** | **string** | Required | The first name of the user |
| **LastName** | **string** | Required | The last name of the user |
| **EmailAddress** | **string** | Required | The user&#39;s email address - to which the account validation email will be sent. For user accounts this should exactly match the Login. |
| **SecondEmailAddress** | **string** | Optional | The user&#39;s second email address. Only allowed for Service users |
| **Login** | **string** | Required | The user&#39;s login username, which must be unique within the system. For user accounts this should exactly match the user&#39;s email address. |
| **AlternativeUserIds** | **Dictionary&lt;string, string&gt;** | Optional | *No description available.* |
| **Roles** | [List&lt;RoleId&gt;](RoleId.md) | Optional | Optional. Any known roles the user should be created with. |
| **Type** | **string** | Required | The type of user (e.g. Personal or Service) |
| **UserExpiry** | **DateTimeOffset?** | Optional | The user&#39;s expiry unix datetime |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new CreateUserRequest(
    firstName: "...",  // required — The first name of the user
    lastName: "...",  // required — The last name of the user
    emailAddress: "...",  // required — The user&#39;s email address - to which the account validation email will be sent. For user accounts this should exactly match the Login.
    secondEmailAddress: "...",  // optional — The user&#39;s second email address. Only allowed for Service users
    login: "...",  // required — The user&#39;s login username, which must be unique within the system. For user accounts this should exactly match the user&#39;s email address.
    alternativeUserIds: ,  // optional
    roles: new List<RoleId>(),  // optional — Optional. Any known roles the user should be created with.
    type: "...",  // required — The type of user (e.g. Personal or Service)
    userExpiry: DateTimeOffset.Now  // optional — The user&#39;s expiry unix datetime
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateUserRequest>(json);
```

- [RoleId](RoleId.md) — used in `Roles`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

