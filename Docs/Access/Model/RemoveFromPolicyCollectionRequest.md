# Finbourne.Sdk.Access.Model.RemoveFromPolicyCollectionRequest

Base properties to create or update a policy collection
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Policies** | [List&lt;PolicyId&gt;](PolicyId.md) | Optional | The identifiers of the Policies to be removed from the collection. |
| **PolicyCollections** | [List&lt;PolicyCollectionId&gt;](PolicyCollectionId.md) | Optional | The identifiers of the PolicyCollections to be removed from the collection. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new RemoveFromPolicyCollectionRequest(
    policies: new List<PolicyId>(),  // optional — The identifiers of the Policies to be removed from the collection.
    policyCollections: new List<PolicyCollectionId>()  // optional — The identifiers of the PolicyCollections to be removed from the collection.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RemoveFromPolicyCollectionRequest>(json);
```


## Related Models

- [PolicyId](PolicyId.md) — used in `Policies`
- [PolicyCollectionId](PolicyCollectionId.md) — used in `PolicyCollections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

