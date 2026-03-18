# Finbourne.Sdk.Lusid.Model.ResultKeyRule

Base class for representing result key rules in LUSID, which describe how to resolve (unit) result data.  This base class should not be directly instantiated; each supported ResultKeyRuleType has a corresponding inherited class.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ResultKeyRuleType** | **string** | Required | The available values are: Invalid, ResultDataKeyRule, PortfolioResultDataKeyRule |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ResultKeyRule(
    resultKeyRuleType: "..."  // required — The available values are: Invalid, ResultDataKeyRule, PortfolioResultDataKeyRule
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResultKeyRule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

