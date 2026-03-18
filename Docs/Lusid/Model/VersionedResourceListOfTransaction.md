# Finbourne.Sdk.Lusid.Model.VersionedResourceListOfTransaction

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VarVersion** | [ModelVersion](ModelVersion.md) | Required | *No description available.* |
| **Values** | [List&lt;Transaction&gt;](Transaction.md) | Required | *No description available.* |
| **Href** | **string** | Optional | *No description available.* |
| **NextPage** | **string** | Optional | *No description available.* |
| **PreviousPage** | **string** | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new VersionedResourceListOfTransaction(
    varVersion: new ModelVersion(...),  // required
    values: new List<Transaction>(),  // required
    href: "...",  // optional
    nextPage: "...",  // optional
    previousPage: "...",  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VersionedResourceListOfTransaction>(json);
```


## Related Models

- [ModelVersion](ModelVersion.md)
- [Transaction](Transaction.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

