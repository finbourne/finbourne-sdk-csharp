# Finbourne.Sdk.Lusid.Model.CreateTaxRuleSetRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | *No description available.* |
| **Description** | **string** | Required | *No description available.* |
| **OutputPropertyKey** | **string** | Required | *No description available.* |
| **Rules** | [List&lt;TaxRule&gt;](TaxRule.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateTaxRuleSetRequest(
    id: new ResourceId(...),  // required
    displayName: "...",  // required
    description: "...",  // required
    outputPropertyKey: "...",  // required
    rules: new List<TaxRule>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateTaxRuleSetRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [TaxRule](TaxRule.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

