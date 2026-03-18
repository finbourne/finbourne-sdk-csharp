# Finbourne.Sdk.Lusid.Model.TaxRuleSet

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | A user-friendly name |
| **Description** | **string** | Required | A description of what this rule set is for |
| **OutputPropertyKey** | **string** | Required | The property key that this rule set will write to |
| **Rules** | [List&lt;TaxRule&gt;](TaxRule.md) | Required | The rules of this rule set, which stipulate what rate to apply (i.e. write to the OutputPropertyKey) under certain conditions |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxRuleSet(
    id: new ResourceId(...),  // required
    displayName: "...",  // required — A user-friendly name
    description: "...",  // required — A description of what this rule set is for
    outputPropertyKey: "...",  // required — The property key that this rule set will write to
    rules: new List<TaxRule>(),  // required — The rules of this rule set, which stipulate what rate to apply (i.e. write to the OutputPropertyKey) under certain conditions
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
var instance = JsonConvert.DeserializeObject<TaxRuleSet>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [TaxRule](TaxRule.md) — used in `Rules`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

