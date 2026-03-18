# Finbourne.Sdk.Identity.Model.UserSchemaResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AlternativeUserIds** | [List&lt;UserSchemaProperty&gt;](UserSchemaProperty.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new UserSchemaResponse(
    alternativeUserIds: new List<UserSchemaProperty>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UserSchemaResponse>(json);
```


## Related Models

- [UserSchemaProperty](UserSchemaProperty.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

