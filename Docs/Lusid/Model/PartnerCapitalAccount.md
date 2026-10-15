# Finbourne.Sdk.Lusid.Model.PartnerCapitalAccount

A partner's capital account statement (PCAP) over a reporting period, in the ILPA row order, with quarter-,  year- and inception-to-date columns and a memo block of commitment balances from the register.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FundId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **InvestorRecordId** | **string** | Required | The investor record identifier of the partner. |
| **Currency** | **string** | Required | The currency the capital account is expressed in, being the fund&#39;s base currency. |
| **PeriodStart** | **DateTimeOffset** | Required | The exclusive start of the reporting period. |
| **PeriodEnd** | **DateTimeOffset** | Required | The inclusive end of the reporting period. |
| **Status** | **string** | Required | Whether the figures are an Estimate or Final. Figures are Final only once a valuation point covering the period end has been finalised. |
| **Rows** | [List&lt;PartnerCapitalAccountRow&gt;](PartnerCapitalAccountRow.md) | Required | The capital account rows, from beginning capital through to ending capital, each with quarter-to-date, year-to-date and inception-to-date columns. |
| **Memo** | [PartnerCapitalAccountMemo](PartnerCapitalAccountMemo.md) | Required | *No description available.* |
| **Foots** | **bool** | Required | Whether the ending capital agrees across the quarter-to-date, year-to-date and inception-to-date columns within tolerance. |
| **FootingDifference** | **decimal** | Required | The largest difference between the ending capital of any two columns. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerCapitalAccount(
    fundId: new ResourceId(...),  // required
    investorRecordId: "...",  // required — The investor record identifier of the partner.
    currency: "...",  // required — The currency the capital account is expressed in, being the fund&#39;s base currency.
    periodStart: DateTimeOffset.Now,  // required — The exclusive start of the reporting period.
    periodEnd: DateTimeOffset.Now,  // required — The inclusive end of the reporting period.
    status: "...",  // required — Whether the figures are an Estimate or Final. Figures are Final only once a valuation point covering the period end has been finalised.
    rows: new List<PartnerCapitalAccountRow>(),  // required — The capital account rows, from beginning capital through to ending capital, each with quarter-to-date, year-to-date and inception-to-date columns.
    memo: new PartnerCapitalAccountMemo(...),  // required
    foots: true,  // required — Whether the ending capital agrees across the quarter-to-date, year-to-date and inception-to-date columns within tolerance.
    footingDifference: 0.0d  // required — The largest difference between the ending capital of any two columns.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnerCapitalAccount>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [PartnerCapitalAccountRow](PartnerCapitalAccountRow.md) — used in `Rows`
- [PartnerCapitalAccountMemo](PartnerCapitalAccountMemo.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

