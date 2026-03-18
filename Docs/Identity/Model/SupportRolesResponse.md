# Finbourne.Sdk.Identity.Model.SupportRolesResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SupportRoles** | [List&lt;SupportRole&gt;](SupportRole.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new SupportRolesResponse(
    supportRoles: new List<SupportRole>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SupportRolesResponse>(json);
```


## Related Models

- [SupportRole](SupportRole.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

