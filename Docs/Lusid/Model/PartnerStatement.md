# Finbourne.Sdk.Lusid.Model.PartnerStatement

A partner's statement: the figures of their position on the fund over a period, fingerprinted so a later  statement can be compared against it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StatementId** | **string** | Required | The identifier of the statement. |
| **FundId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **InvestorRecordId** | **string** | Required | The investor record the statement is for. |
| **PeriodStart** | **DateTimeOffset** | Required | The start of the statement period, exclusive. |
| **PeriodEnd** | **DateTimeOffset** | Required | The end of the statement period, inclusive. |
| **NavTypeCode** | **string** | Required | The NAV type to produce the statement under. Defaults to the fund&#39;s primary NAV type. |
| **Currency** | **string** | Required | The currency of the statement. |
| **Lines** | [List&lt;PartnerStatementLine&gt;](PartnerStatementLine.md) | Required | The figures on the statement. |
| **Fingerprint** | **string** | Required | A hash of the statement&#39;s content, so two statements can be told apart. |
| **ProducedAsAt** | **DateTimeOffset** | Required | When the statement was produced. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerStatement(
    statementId: "...",  // required — The identifier of the statement.
    fundId: new ResourceId(...),  // required
    investorRecordId: "...",  // required — The investor record the statement is for.
    periodStart: DateTimeOffset.Now,  // required — The start of the statement period, exclusive.
    periodEnd: DateTimeOffset.Now,  // required — The end of the statement period, inclusive.
    navTypeCode: "...",  // required — The NAV type to produce the statement under. Defaults to the fund&#39;s primary NAV type.
    currency: "...",  // required — The currency of the statement.
    lines: new List<PartnerStatementLine>(),  // required — The figures on the statement.
    fingerprint: "...",  // required — A hash of the statement&#39;s content, so two statements can be told apart.
    producedAsAt: DateTimeOffset.Now  // required — When the statement was produced.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnerStatement>(json);
```

- [ResourceId](ResourceId.md)
- [PartnerStatementLine](PartnerStatementLine.md) — used in `Lines`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

