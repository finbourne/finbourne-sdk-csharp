# Finbourne.Sdk.Lusid.Model.SettlementActivityQuery

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAt** | **DateTimeOffset?** | Optional | The asAt time at which to query settlement activity. Defaults to latest. |
| **PortfolioEntityIds** | [List&lt;PortfolioEntityId&gt;](PortfolioEntityId.md) | Optional | The portfolios and / or portfolio groups to query. At least one entry is required. |
| **StartActivityDate** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | Lower bound (inclusive) of the activity date range. If not set, no lower bound is applied. |
| **EndActivityDate** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | Upper bound (inclusive) of the activity date range. Defaults to the current date and time. Treated as effectiveAt. |
| **Filter** | **string** | Optional | A LUSID standard filter expression. Supports traversal into transaction and settlementInstruction. |
| **SettlementInstructionPropertyKeys** | **List&lt;string&gt;** | Optional | Settlement instruction property keys to populate on the response. Behaviour matches BuildSettlementInstructions. |
| **TransactionPropertyKeys** | **List&lt;string&gt;** | Optional | Transaction property keys to populate on the response. Behaviour matches BuildSettlementInstructions. |
| **Limit** | **int?** | Optional | Page size limit; standard pagination control. Defaults to 5000. |
| **Page** | **string** | Optional | Pagination cursor returned by a previous response. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SettlementActivityQuery(
    asAt: DateTimeOffset.Now,  // optional — The asAt time at which to query settlement activity. Defaults to latest.
    portfolioEntityIds: new List<PortfolioEntityId>(),  // optional — The portfolios and / or portfolio groups to query. At least one entry is required.
    startActivityDate: new DateTimeOrCutLabel(...),  // optional — Lower bound (inclusive) of the activity date range. If not set, no lower bound is applied.
    endActivityDate: new DateTimeOrCutLabel(...),  // optional — Upper bound (inclusive) of the activity date range. Defaults to the current date and time. Treated as effectiveAt.
    filter: "...",  // optional — A LUSID standard filter expression. Supports traversal into transaction and settlementInstruction.
    settlementInstructionPropertyKeys: ,  // optional — Settlement instruction property keys to populate on the response. Behaviour matches BuildSettlementInstructions.
    transactionPropertyKeys: ,  // optional — Transaction property keys to populate on the response. Behaviour matches BuildSettlementInstructions.
    limit: 0,  // optional — Page size limit; standard pagination control. Defaults to 5000.
    page: "..."  // optional — Pagination cursor returned by a previous response.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SettlementActivityQuery>(json);
```

- [PortfolioEntityId](PortfolioEntityId.md) — used in `PortfolioEntityIds`
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `StartActivityDate`
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EndActivityDate`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

