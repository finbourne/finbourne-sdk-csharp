# Finbourne.Sdk.Lusid.Model.InvestmentPortfolioIdentifier

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | A client-defined key used to identify the Investment Portfolio, unique within the Investment Account |
| **Scope** | **string** | Required | The scope of the Investment Portfolio. |
| **Identifiers** | **Dictionary&lt;string, string&gt;** | Required | The code identifier of the Investment Portfolio. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InvestmentPortfolioIdentifier(
    key: "...",  // required — A client-defined key used to identify the Investment Portfolio, unique within the Investment Account
    scope: "...",  // required — The scope of the Investment Portfolio.
    identifiers:   // required — The code identifier of the Investment Portfolio.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InvestmentPortfolioIdentifier>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

