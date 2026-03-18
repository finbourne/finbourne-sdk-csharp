# Finbourne.Sdk.Lusid.Model.InvestmentPortfolio

An Investment Portfolio of an Investment Account.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Optional | A client-defined key used to identify the Investment Portfolio, unique within the Investment Account |
| **Scope** | **string** | Optional | The scope of the Investment Portfolio |
| **Identifiers** | **Dictionary&lt;string, string&gt;** | Optional | The code identifier of the Investment Portfolio |
| **EntityUniqueId** | **string** | Optional | The unique Portfolio entity identifier |
| **Portfolio** | [Portfolio](Portfolio.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InvestmentPortfolio(
    key: "...",  // optional — A client-defined key used to identify the Investment Portfolio, unique within the Investment Account
    scope: "...",  // optional — The scope of the Investment Portfolio
    identifiers: ,  // optional — The code identifier of the Investment Portfolio
    entityUniqueId: "...",  // optional — The unique Portfolio entity identifier
    portfolio: new Portfolio(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InvestmentPortfolio>(json);
```

- [Portfolio](Portfolio.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

