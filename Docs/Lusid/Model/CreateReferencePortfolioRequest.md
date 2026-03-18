# Finbourne.Sdk.Lusid.Model.CreateReferencePortfolioRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The name of the reference portfolio. |
| **Description** | **string** | Optional | A long form text description of the portfolio. |
| **Code** | **string** | Required | Unique identifier for the portfolio. |
| **Created** | **DateTimeOffset?** | Optional | The original creation date, defaults to today if not specified when creating a portfolio. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | Portfolio properties to add to the portfolio. |
| **InstrumentScopes** | **List&lt;string&gt;** | Optional | Instrument Scopes. |
| **BaseCurrency** | **string** | Optional | The base currency of the transaction portfolio in ISO 4217 currency code format. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateReferencePortfolioRequest(
    displayName: "...",  // required — The name of the reference portfolio.
    description: "...",  // optional — A long form text description of the portfolio.
    code: "...",  // required — Unique identifier for the portfolio.
    created: DateTimeOffset.Now,  // optional — The original creation date, defaults to today if not specified when creating a portfolio.
    properties: new Property(...),  // optional — Portfolio properties to add to the portfolio.
    instrumentScopes: ,  // optional — Instrument Scopes.
    baseCurrency: "..."  // optional — The base currency of the transaction portfolio in ISO 4217 currency code format.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateReferencePortfolioRequest>(json);
```

- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

