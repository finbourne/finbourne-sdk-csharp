# Finbourne.Sdk.Access.Model.PolicyCollectionUpdateRequest

Update an existing PolicyCollection
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Policies** | [List&lt;PolicyId&gt;](PolicyId.md) | Optional | The identifiers of the Policies in this collection |
| **Metadata** | **Dictionary&lt;string, List&lt;EntitlementMetadata&gt;&gt;** | Optional | Any relevant metadata associated with this resource for controlling access to this resource |
| **PolicyCollections** | [List&lt;PolicyCollectionId&gt;](PolicyCollectionId.md) | Optional | The identifiers of the PolicyCollections in this collection |
| **Description** | **string** | Optional | A description of this policy collection |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new PolicyCollectionUpdateRequest(
    policies: new List<PolicyId>(),  // optional — The identifiers of the Policies in this collection
    metadata: ,  // optional — Any relevant metadata associated with this resource for controlling access to this resource
    policyCollections: new List<PolicyCollectionId>(),  // optional — The identifiers of the PolicyCollections in this collection
    description: "..."  // optional — A description of this policy collection
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PolicyCollectionUpdateRequest>(json);
```


## Related Models

- [PolicyId](PolicyId.md) — used in `Policies`
- [PolicyCollectionId](PolicyCollectionId.md) — used in `PolicyCollections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

