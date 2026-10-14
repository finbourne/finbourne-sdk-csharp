# Finbourne.Sdk.Lusid.Model.DecoratedComplianceRunSummaryRequest

Specification for retrieving a decorated compliance run summary, optionally restricted to a  set of portfolios and/or portfolio groups.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PortfolioEntityIds** | [List&lt;PortfolioEntityId&gt;](PortfolioEntityId.md) | Optional | *No description available.* |
| **PropertyKeys** | **List&lt;string&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DecoratedComplianceRunSummaryRequest(
    runId: new ResourceId(...),  // required
    portfolioEntityIds: new List<PortfolioEntityId>(),  // optional
    propertyKeys:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DecoratedComplianceRunSummaryRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [PortfolioEntityId](PortfolioEntityId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

