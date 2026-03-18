# Finbourne.Sdk.Configuration.Model.PersonalAccessToken

Representation of a Personal Access Token under a Configuration Item format.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **string** | Required | Value of the Personal Access Token. *(read-only)* |
| **Type** | **string** | Required | The type of the Personal Access Token. *(read-only)* |
| **Description** | **string** | Required | The description of the Personal Access Token. *(read-only)* |
| **Ref** | **string** | Required | The reference to the Personal Access Token *(read-only)* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Configuration.Model;

var instance = new PersonalAccessToken(
    value: "...",  // required — Value of the Personal Access Token.
    type: "...",  // required — The type of the Personal Access Token.
    description: "...",  // required — The description of the Personal Access Token.
    varRef: "...",  // required — The reference to the Personal Access Token
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PersonalAccessToken>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

