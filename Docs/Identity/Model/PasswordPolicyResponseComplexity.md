# Finbourne.Sdk.Identity.Model.PasswordPolicyResponseComplexity

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MinLength** | **int** | Required | The minimum length for a password |
| **ExcludeFirstName** | **bool** | Required | Rule determining whether a user&#39;s first name should be permitted in their password |
| **ExcludeLastName** | **bool** | Required | Rule determining whether a user&#39;s last name should be permitted in their password |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new PasswordPolicyResponseComplexity(
    minLength: 0,  // required — The minimum length for a password
    excludeFirstName: true,  // required — Rule determining whether a user&#39;s first name should be permitted in their password
    excludeLastName: true  // required — Rule determining whether a user&#39;s last name should be permitted in their password
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PasswordPolicyResponseComplexity>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

