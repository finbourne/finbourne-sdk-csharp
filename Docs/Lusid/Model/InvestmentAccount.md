# Finbourne.Sdk.Lusid.Model.InvestmentAccount

Representation of an Investment Account on the LUSID API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Optional | The scope in which the Investment Account lies. |
| **Identifiers** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | Unique client-defined identifiers of the Investment Account. |
| **DisplayName** | **string** | Optional | The display name of the Investment Account |
| **Description** | **string** | Optional | The description of the Investment Account |
| **AccountType** | **string** | Optional | The type of the of the Investment Account. |
| **AccountHolders** | [List&lt;AccountHolder&gt;](AccountHolder.md) | Optional | The Account Holders of the Investment Account. |
| **InvestmentPortfolios** | [List&lt;InvestmentPortfolio&gt;](InvestmentPortfolio.md) | Optional | The Investment Portfolios of the Investment Account. |
| **LusidInvestmentAccountId** | **string** | Optional | The unique LUSID Investment Account Identifier of the Investment Account. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties associated to the Investment Account. |
| **Relationships** | [List&lt;Relationship&gt;](Relationship.md) | Optional | A set of relationships associated to the Investment Account. |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InvestmentAccount(
    scope: "...",  // optional — The scope in which the Investment Account lies.
    identifiers: new Property(...),  // optional — Unique client-defined identifiers of the Investment Account.
    displayName: "...",  // optional — The display name of the Investment Account
    description: "...",  // optional — The description of the Investment Account
    accountType: "...",  // optional — The type of the of the Investment Account.
    accountHolders: new List<AccountHolder>(),  // optional — The Account Holders of the Investment Account.
    investmentPortfolios: new List<InvestmentPortfolio>(),  // optional — The Investment Portfolios of the Investment Account.
    lusidInvestmentAccountId: "...",  // optional — The unique LUSID Investment Account Identifier of the Investment Account.
    properties: new Property(...),  // optional — A set of properties associated to the Investment Account.
    relationships: new List<Relationship>(),  // optional — A set of relationships associated to the Investment Account.
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InvestmentAccount>(json);
```

- [Property](Property.md) — used in `Identifiers`
- [AccountHolder](AccountHolder.md) — used in `AccountHolders`
- [InvestmentPortfolio](InvestmentPortfolio.md) — used in `InvestmentPortfolios`
- [Property](Property.md) — used in `Properties`
- [Relationship](Relationship.md) — used in `Relationships`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

