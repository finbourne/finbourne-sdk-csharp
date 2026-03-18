# Finbourne.Sdk.Lusid.Model.RulesInterval

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveRange** | [DateRange](DateRange.md) | Required | *No description available.* |
| **Rules** | [List&lt;AmortisationRule&gt;](AmortisationRule.md) | Required | The rules of this rule set. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RulesInterval(
    effectiveRange: new DateRange(...),  // required
    rules: new List<AmortisationRule>()  // required — The rules of this rule set.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RulesInterval>(json);
```


## Related Models

- [DateRange](DateRange.md)
- [AmortisationRule](AmortisationRule.md) — used in `Rules`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

