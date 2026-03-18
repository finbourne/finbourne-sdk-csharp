# Finbourne.Sdk.Access.Model.NonTransitiveSupervisorRoleResource

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Roles** | **List&lt;Dictionary&lt;string, string&gt;&gt;** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new NonTransitiveSupervisorRoleResource(
    roles:   // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<NonTransitiveSupervisorRoleResource>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

