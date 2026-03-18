# Finbourne.Sdk.Lusid.Model.AmortisationRule

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name of the rule. |
| **Description** | **string** | Optional | A description of the rule. |
| **Filter** | **string** | Required | The filter for this rule. |
| **AmortisationMethod** | **string** | Required | The filter for this rule. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AmortisationRule(
    name: "...",  // required — The name of the rule.
    description: "...",  // optional — A description of the rule.
    filter: "...",  // required — The filter for this rule.
    amortisationMethod: "..."  // required — The filter for this rule.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AmortisationRule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

