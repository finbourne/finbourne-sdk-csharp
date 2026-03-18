# Finbourne.Sdk.Identity.Model.SetPasswordResponse

The result of setting a password
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **UpdatedAt** | **DateTimeOffset** | Required | The date and time at which the password was successfully updated |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new SetPasswordResponse(
    updatedAt: DateTimeOffset.Now,  // required — The date and time at which the password was successfully updated
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SetPasswordResponse>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

