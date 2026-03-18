# Finbourne.Sdk.Lusid.Model.CleardownModuleResponse

A Cleardown Module definition
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **CleardownModuleCode** | **string** | Required | The code of the Cleardown Module. |
| **ChartOfAccountsId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | The name of the Cleardown Module. |
| **Description** | **string** | Optional | A description for the Cleardown Module. |
| **Rules** | [List&lt;CleardownModuleRule&gt;](CleardownModuleRule.md) | Optional | The Cleardown Rules that apply for the Cleardown Module. Rules are evaluated in the order they occur in this collection. |
| **Status** | **string** | Required | The Cleardown Module status. Can be Active, Inactive or Deleted. Defaults to Active. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CleardownModuleResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    cleardownModuleCode: "...",  // required — The code of the Cleardown Module.
    chartOfAccountsId: new ResourceId(...),  // required
    displayName: "...",  // required — The name of the Cleardown Module.
    description: "...",  // optional — A description for the Cleardown Module.
    rules: new List<CleardownModuleRule>(),  // optional — The Cleardown Rules that apply for the Cleardown Module. Rules are evaluated in the order they occur in this collection.
    status: "...",  // required — The Cleardown Module status. Can be Active, Inactive or Deleted. Defaults to Active.
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
var instance = JsonConvert.DeserializeObject<CleardownModuleResponse>(json);
```

- [ResourceId](ResourceId.md)
- [CleardownModuleRule](CleardownModuleRule.md) — used in `Rules`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

