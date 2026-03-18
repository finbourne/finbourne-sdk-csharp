# Finbourne.Sdk.Lusid.Model.PortfoliosReconciliationRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | [PortfolioReconciliationRequest](PortfolioReconciliationRequest.md) | Required | *No description available.* |
| **Right** | [PortfolioReconciliationRequest](PortfolioReconciliationRequest.md) | Required | *No description available.* |
| **InstrumentPropertyKeys** | **List&lt;string&gt;** | Required | Instrument properties to be included with any identified breaks. These properties will be in the effective and AsAt dates of the left portfolio |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfoliosReconciliationRequest(
    left: new PortfolioReconciliationRequest(...),  // required
    right: new PortfolioReconciliationRequest(...),  // required
    instrumentPropertyKeys:   // required — Instrument properties to be included with any identified breaks. These properties will be in the effective and AsAt dates of the left portfolio
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfoliosReconciliationRequest>(json);
```


## Related Models

- [PortfolioReconciliationRequest](PortfolioReconciliationRequest.md)
- [PortfolioReconciliationRequest](PortfolioReconciliationRequest.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

