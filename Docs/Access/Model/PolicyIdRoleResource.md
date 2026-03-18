# Finbourne.Sdk.Access.Model.PolicyIdRoleResource

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Policies** | [List&lt;PolicyId&gt;](PolicyId.md) | Optional | *No description available.* |
| **PolicyCollections** | [List&lt;PolicyCollectionId&gt;](PolicyCollectionId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new PolicyIdRoleResource(
    policies: new List<PolicyId>(),  // optional
    policyCollections: new List<PolicyCollectionId>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PolicyIdRoleResource>(json);
```


## Related Models

- [PolicyId](PolicyId.md)
- [PolicyCollectionId](PolicyCollectionId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

