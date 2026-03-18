# Finbourne.Sdk.Lusid.Model.PortfolioReconciliationRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **EffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Required | The effective date of the portfolio |
| **AsAt** | **DateTimeOffset?** | Optional | Optional. The AsAt date of the portfolio |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioReconciliationRequest(
    portfolioId: new ResourceId(...),  // required
    effectiveAt: new DateTimeOrCutLabel(...),  // required — The effective date of the portfolio
    asAt: DateTimeOffset.Now  // optional — Optional. The AsAt date of the portfolio
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioReconciliationRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveAt`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

