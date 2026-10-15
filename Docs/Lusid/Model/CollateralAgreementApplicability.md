# Finbourne.Sdk.Lusid.Model.CollateralAgreementApplicability

The portfolios a collateral agreement currently covers, according to its applicability filter.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **ApplicabilityFilter** | **string** | Required | The applicability filter that was evaluated. Only its clauses on portfolio fields are applied to select the portfolios returned. |
| **Portfolios** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | The portfolios matching the applicability filter, up to the requested limit. |
| **HasMorePortfolios** | **bool** | Required | Whether more portfolios match the filter than were returned. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CollateralAgreementApplicability(
    id: new ResourceId(...),  // required
    applicabilityFilter: "...",  // required — The applicability filter that was evaluated. Only its clauses on portfolio fields are applied to select the portfolios returned.
    portfolios: new List<ResourceId>(),  // required — The portfolios matching the applicability filter, up to the requested limit.
    hasMorePortfolios: true  // required — Whether more portfolios match the filter than were returned.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CollateralAgreementApplicability>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md) — used in `Portfolios`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

