# Finbourne.Sdk.Lusid.Model.PortfolioResultDataKeyRule

> **Inherits from:** [ResultKeyRule](ResultKeyRule.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Supplier** | **string** | Required | the result resource supplier (where the data comes from) |
| **DataScope** | **string** | Required | which is the scope in which the data should be found |
| **DocumentCode** | **string** | Required | document code that defines which document is desired |
| **QuoteInterval** | **string** | Optional | Shorthand for the time interval used to select result data. This must be a dot-separated string              specifying a start and end date, for example &#39;5D.0D&#39; to look back 5 days from today (0 days ago). |
| **AsAt** | **DateTimeOffset?** | Optional | The AsAt predicate specification. |
| **PortfolioCode** | **string** | Optional | *No description available.* |
| **PortfolioScope** | **string** | Optional | *No description available.* |
| **ResultKeyRuleType** | **string** | Required | The available values are: Invalid, ResultDataKeyRule, PortfolioResultDataKeyRule Default: `ResultKeyRuleTypeEnum.PortfolioResultDataKeyRule` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioResultDataKeyRule(
    supplier: "...",  // required — the result resource supplier (where the data comes from)
    dataScope: "...",  // required — which is the scope in which the data should be found
    documentCode: "...",  // required — document code that defines which document is desired
    quoteInterval: "...",  // optional — Shorthand for the time interval used to select result data. This must be a dot-separated string              specifying a start and end date, for example &#39;5D.0D&#39; to look back 5 days from today (0 days ago).
    asAt: DateTimeOffset.Now,  // optional — The AsAt predicate specification.
    portfolioCode: "...",  // optional
    portfolioScope: "...",  // optional
    resultKeyRuleType: "..."  // required — The available values are: Invalid, ResultDataKeyRule, PortfolioResultDataKeyRule
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioResultDataKeyRule>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

