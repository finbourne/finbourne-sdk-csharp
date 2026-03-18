# Finbourne.Sdk.Identity.Model.UpdateUserRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FirstName** | **string** | Required | *No description available.* |
| **LastName** | **string** | Required | *No description available.* |
| **EmailAddress** | **string** | Required | *No description available.* |
| **SecondEmailAddress** | **string** | Optional | *No description available.* |
| **Login** | **string** | Required | The user&#39;s login username, in the form of an email address, which must be unique within the system. For user accounts this should exactly match the user&#39;s email address. |
| **AlternativeUserIds** | **Dictionary&lt;string, string&gt;** | Optional | *No description available.* |
| **Roles** | [List&lt;RoleId&gt;](RoleId.md) | Optional | Deprecated. To update a user&#39;s roles use the AddUserToRole and RemoveUserFromRole endpoints |
| **UserExpiry** | **DateTimeOffset?** | Optional | The user&#39;s expiry unix datetime |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new UpdateUserRequest(
    firstName: "...",  // required
    lastName: "...",  // required
    emailAddress: "...",  // required
    secondEmailAddress: "...",  // optional
    login: "...",  // required — The user&#39;s login username, in the form of an email address, which must be unique within the system. For user accounts this should exactly match the user&#39;s email address.
    alternativeUserIds: ,  // optional
    roles: new List<RoleId>(),  // optional — Deprecated. To update a user&#39;s roles use the AddUserToRole and RemoveUserFromRole endpoints
    userExpiry: DateTimeOffset.Now  // optional — The user&#39;s expiry unix datetime
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateUserRequest>(json);
```

- [RoleId](RoleId.md) — used in `Roles`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

