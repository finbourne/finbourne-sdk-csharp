# Finbourne.Sdk.Lusid.Model.FeeType

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | The name of the fee type. |
| **Description** | **string** | Required | The description of the fee type. |
| **ComponentTransactions** | [List&lt;ComponentTransaction&gt;](ComponentTransaction.md) | Required | A set of component transactions that relate to the fee type to be created. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FeeType(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    id: new ResourceId(...),  // required
    displayName: "...",  // required — The name of the fee type.
    description: "...",  // required — The description of the fee type.
    componentTransactions: new List<ComponentTransaction>(),  // required — A set of component transactions that relate to the fee type to be created.
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FeeType>(json);
```

- [ResourceId](ResourceId.md)
- [ComponentTransaction](ComponentTransaction.md) — used in `ComponentTransactions`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

