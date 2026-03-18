# Finbourne.Sdk.Lusid.Model.UpdateTaxRuleSetRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | *No description available.* |
| **Description** | **string** | Required | *No description available.* |
| **Rules** | [List&lt;TaxRule&gt;](TaxRule.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateTaxRuleSetRequest(
    displayName: "...",  // required
    description: "...",  // required
    rules: new List<TaxRule>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateTaxRuleSetRequest>(json);
```

- [TaxRule](TaxRule.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

