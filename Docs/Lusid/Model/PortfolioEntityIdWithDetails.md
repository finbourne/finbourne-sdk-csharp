# Finbourne.Sdk.Lusid.Model.PortfolioEntityIdWithDetails

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **Scope** | **string** | Required | The scope within which the portfolio or portfolio group lives. |
| **Code** | **string** | Required | Portfolio name or code. |
| **PortfolioEntityType** | **string** | Optional | String identifier for portfolio e.g. \&quot;SinglePortfolio\&quot; and \&quot;GroupPortfolio\&quot;. If not specified, it is assumed to be a single portfolio. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioEntityIdWithDetails(
    displayName: "...",  // optional
    description: "...",  // optional
    scope: "...",  // required — The scope within which the portfolio or portfolio group lives.
    code: "...",  // required — Portfolio name or code.
    portfolioEntityType: "..."  // optional — String identifier for portfolio e.g. \&quot;SinglePortfolio\&quot; and \&quot;GroupPortfolio\&quot;. If not specified, it is assumed to be a single portfolio.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioEntityIdWithDetails>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

