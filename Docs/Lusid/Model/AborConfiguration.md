# Finbourne.Sdk.Lusid.Model.AborConfiguration

An AborConfiguration entity.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Optional | The name of the Abor Configuration. |
| **Description** | **string** | Optional | A description for the Abor Configuration. |
| **RecipeId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **ChartOfAccountsId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PostingModuleCodes** | **List&lt;string&gt;** | Optional | The Posting Module Codes from which the rules to be applied are retrieved. |
| **CleardownModuleCodes** | **List&lt;string&gt;** | Optional | The Cleardown Module Codes from which the rules to be applied are retrieved. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the Abor Configuration. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AborConfiguration(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    id: new ResourceId(...),  // required
    displayName: "...",  // optional — The name of the Abor Configuration.
    description: "...",  // optional — A description for the Abor Configuration.
    recipeId: new ResourceId(...),  // optional
    chartOfAccountsId: new ResourceId(...),  // required
    postingModuleCodes: ,  // optional — The Posting Module Codes from which the rules to be applied are retrieved.
    cleardownModuleCodes: ,  // optional — The Cleardown Module Codes from which the rules to be applied are retrieved.
    properties: new Property(...),  // optional — A set of properties for the Abor Configuration.
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
var instance = JsonConvert.DeserializeObject<AborConfiguration>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [Property](Property.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

