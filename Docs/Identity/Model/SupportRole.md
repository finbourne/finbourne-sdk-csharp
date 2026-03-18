# Finbourne.Sdk.Identity.Model.SupportRole

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Label** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **RoleIdentifier** | **Dictionary&lt;string, string&gt;** | Optional | *No description available.* |
| **InternalIdentifier** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new SupportRole(
    label: "...",  // optional
    description: "...",  // optional
    roleIdentifier: ,  // optional
    internalIdentifier: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SupportRole>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

