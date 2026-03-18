# Finbourne.Sdk.Access.Model.PolicyCollectionResponse

A PolicyCollection encapsulating one or more Policies and PolicyCollections
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [PolicyCollectionId](PolicyCollectionId.md) | Optional | *No description available.* |
| **Policies** | [List&lt;PolicyId&gt;](PolicyId.md) | Optional | The identifiers of the Policies in this collection |
| **PolicyCollections** | [List&lt;PolicyCollectionId&gt;](PolicyCollectionId.md) | Optional | The identifiers of the PolicyCollections in this collection |
| **Description** | **string** | Optional | A description of this policy collection |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new PolicyCollectionResponse(
    id: new PolicyCollectionId(...),  // optional
    policies: new List<PolicyId>(),  // optional — The identifiers of the Policies in this collection
    policyCollections: new List<PolicyCollectionId>(),  // optional — The identifiers of the PolicyCollections in this collection
    description: "...",  // optional — A description of this policy collection
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PolicyCollectionResponse>(json);
```


## Related Models

- [PolicyCollectionId](PolicyCollectionId.md)
- [PolicyId](PolicyId.md) — used in `Policies`
- [PolicyCollectionId](PolicyCollectionId.md) — used in `PolicyCollections`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

