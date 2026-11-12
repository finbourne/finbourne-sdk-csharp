# Finbourne.Sdk.Lusid.Model.RunComplianceV3Request

A request to run one or more V3 compliance rules against a portfolio group, valuing holdings with the  supplied recipe. The pre-trade variant additionally includes the group's live order flow.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | *No description available.* |
| **PortfolioGroupId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **RecipeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **EffectiveAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **AsAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **EvaluationMode** | **string** | Optional | Available values: PerPortfolio, GroupTotal. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RunComplianceV3Request(
    ruleIds: new List<ResourceId>(),  // required
    portfolioGroupId: new ResourceId(...),  // required
    recipeId: new ResourceId(...),  // required
    effectiveAt: DateTimeOffset.Now,  // optional
    asAt: DateTimeOffset.Now,  // optional
    evaluationMode: "..."  // optional — Available values: PerPortfolio, GroupTotal.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RunComplianceV3Request>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

