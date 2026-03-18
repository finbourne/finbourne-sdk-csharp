# Finbourne.Sdk.Lusid.Model.UpsertInvestmentAccountRequest

Request to create or update an investor record
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope in which the Investment Account lies. |
| **Identifiers** | [Dictionary&lt;string, Property&gt;](Property.md) | Required | Unique client-defined identifiers of the Investment Account. |
| **DisplayName** | **string** | Required | The display name of the Investment Account |
| **Description** | **string** | Optional | The description of the Investment Account |
| **AccountType** | **string** | Required | The type of the of the Investment Account. |
| **AccountHolders** | [List&lt;AccountHolderIdentifier&gt;](AccountHolderIdentifier.md) | Optional | The identification of the account holders associated with this investment account |
| **InvestmentPortfolios** | [List&lt;InvestmentPortfolioIdentifier&gt;](InvestmentPortfolioIdentifier.md) | Optional | The identification of the investment portfolios associated with this investment account |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties associated to the Investment Account. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertInvestmentAccountRequest(
    scope: "...",  // required — The scope in which the Investment Account lies.
    identifiers: new Property(...),  // required — Unique client-defined identifiers of the Investment Account.
    displayName: "...",  // required — The display name of the Investment Account
    description: "...",  // optional — The description of the Investment Account
    accountType: "...",  // required — The type of the of the Investment Account.
    accountHolders: new List<AccountHolderIdentifier>(),  // optional — The identification of the account holders associated with this investment account
    investmentPortfolios: new List<InvestmentPortfolioIdentifier>(),  // optional — The identification of the investment portfolios associated with this investment account
    properties: new Property(...)  // optional — A set of properties associated to the Investment Account.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertInvestmentAccountRequest>(json);
```

- [Property](Property.md) — used in `Identifiers`
- [AccountHolderIdentifier](AccountHolderIdentifier.md) — used in `AccountHolders`
- [InvestmentPortfolioIdentifier](InvestmentPortfolioIdentifier.md) — used in `InvestmentPortfolios`
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

