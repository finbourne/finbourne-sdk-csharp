# Finbourne.Sdk.Access.Model.AddPolicyCollectionToRoleRequest

Request body used to add Policy Collections to a Role
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PolicyCollections** | [List&lt;PolicyCollectionId&gt;](PolicyCollectionId.md) | Required | Identifiers of policy collections to add to a role |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new AddPolicyCollectionToRoleRequest(
    policyCollections: new List<PolicyCollectionId>()  // required — Identifiers of policy collections to add to a role
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AddPolicyCollectionToRoleRequest>(json);
```


## Related Models

- [PolicyCollectionId](PolicyCollectionId.md) — used in `PolicyCollections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

