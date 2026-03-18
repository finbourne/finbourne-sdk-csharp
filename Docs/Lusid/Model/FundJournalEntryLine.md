# Finbourne.Sdk.Lusid.Model.FundJournalEntryLine

A Journal Entry line entity specifically for fund valuation point lines.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AccountingDate** | **DateTimeOffset** | Required | The Journal Entry Line accounting date. |
| **ActivityDate** | **DateTimeOffset** | Required | The actual date of the activity. Differs from the accounting date when creating journals that would occur in a closed period. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **InstrumentId** | **string** | Required | To indicate the instrument of the transaction that the Journal Entry Line posted for, if applicable. |
| **InstrumentScope** | **string** | Required | The scope in which the Journal Entry Line instrument is in. |
| **SubHoldingKeys** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The sub-holding properties which are part of the AccountingKey. |
| **TaxLotId** | **string** | Optional | If the holding type is &#39;B&#39; (settled cash balance), this is 1. Otherwise, this is the ID of a tax lot if applicable, or the source ID of the original transaction if not. |
| **GeneralLedgerAccountCode** | **string** | Required | The code of the account in the general ledger the Journal Entry was posted to. |
| **Local** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **Base** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **Units** | **decimal** | Required | Units held for the Journal Entry Line. |
| **PostingModuleCode** | **string** | Optional | The code of the posting module where the posting rules derived the Journal Entry lines. |
| **PostingRule** | **string** | Required | The rule generating the Journal Entry Line. |
| **AsAtDate** | **DateTimeOffset** | Required | The corresponding input date and time of the Transaction generating the Journal Entry Line. |
| **ActivitiesDescription** | **string** | Optional | This would be the description of the business activities this Journal Entry Line is for. |
| **SourceType** | **string** | Required | So far are 4 types: LusidTxn, LusidValuation, Manual and External. |
| **SourceId** | **string** | Required | For the Lusid Source Type this will be the txn Id. For the rest will be what the user populates. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the Abor. |
| **MovementName** | **string** | Optional | If the JE Line is generated from a transaction, the name of the side in the transaction type&#39;s movement. If from a valuation, this is &#39;MarkToMarket&#39;. |
| **HoldingType** | **string** | Required | One of the LUSID holding types such as &#39;P&#39; for position or &#39;B&#39; for settled cash balance. |
| **EconomicBucket** | **string** | Required | LUSID automatically categorises a JE Line into a broad economic bucket such as &#39;NA_Cost&#39; or &#39;PL_RealPriceGL&#39;. |
| **EconomicBucketComponent** | **string** | Optional | Sub bucket of the economic bucket. |
| **EconomicBucketVariant** | **string** | Optional | Categorisation of a Mark-to-market journal entry line into LongTerm or ShortTerm based on whether the ActivityDate is more than a year after the purchase trade date or not. |
| **Levels** | **List&lt;string&gt;** | Optional | Resolved data from the general ledger profile where the GeneralLedgerProfileCode is specified in the GetJournalEntryLines request body. |
| **SourceLevels** | **List&lt;string&gt;** | Optional | Source data from the general ledger profile where the GeneralLedgerProfileCode is specified in the GetJournalEntryLines request body. |
| **MovementSign** | **string** | Optional | Indicates if the Journal Entry Line corresponds to a Long or Short movement. |
| **HoldingSign** | **string** | Optional | Indicates if the Journal Entry Line is operating against a Long or Short holding. |
| **LedgerColumn** | **string** | Optional | Indicates if the Journal Entry Line is credit or debit. |
| **JournalEntryLineType** | **string** | Optional | Indicates the Journal Entry Line type |
| **ShareClassBreakdowns** | [List&lt;JournalEntryLineShareClassBreakdown&gt;](JournalEntryLineShareClassBreakdown.md) | Optional | Share Class breakdown data for this Journal Entry Line. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundJournalEntryLine(
    accountingDate: DateTimeOffset.Now,  // required — The Journal Entry Line accounting date.
    activityDate: DateTimeOffset.Now,  // required — The actual date of the activity. Differs from the accounting date when creating journals that would occur in a closed period.
    portfolioId: new ResourceId(...),  // required
    instrumentId: "...",  // required — To indicate the instrument of the transaction that the Journal Entry Line posted for, if applicable.
    instrumentScope: "...",  // required — The scope in which the Journal Entry Line instrument is in.
    subHoldingKeys: new PerpetualProperty(...),  // optional — The sub-holding properties which are part of the AccountingKey.
    taxLotId: "...",  // optional — If the holding type is &#39;B&#39; (settled cash balance), this is 1. Otherwise, this is the ID of a tax lot if applicable, or the source ID of the original transaction if not.
    generalLedgerAccountCode: "...",  // required — The code of the account in the general ledger the Journal Entry was posted to.
    local: new CurrencyAndAmount(...),  // required
    varBase: new CurrencyAndAmount(...),  // required
    units: 0.0d,  // required — Units held for the Journal Entry Line.
    postingModuleCode: "...",  // optional — The code of the posting module where the posting rules derived the Journal Entry lines.
    postingRule: "...",  // required — The rule generating the Journal Entry Line.
    asAtDate: DateTimeOffset.Now,  // required — The corresponding input date and time of the Transaction generating the Journal Entry Line.
    activitiesDescription: "...",  // optional — This would be the description of the business activities this Journal Entry Line is for.
    sourceType: "...",  // required — So far are 4 types: LusidTxn, LusidValuation, Manual and External.
    sourceId: "...",  // required — For the Lusid Source Type this will be the txn Id. For the rest will be what the user populates.
    properties: new Property(...),  // optional — A set of properties for the Abor.
    movementName: "...",  // optional — If the JE Line is generated from a transaction, the name of the side in the transaction type&#39;s movement. If from a valuation, this is &#39;MarkToMarket&#39;.
    holdingType: "...",  // required — One of the LUSID holding types such as &#39;P&#39; for position or &#39;B&#39; for settled cash balance.
    economicBucket: "...",  // required — LUSID automatically categorises a JE Line into a broad economic bucket such as &#39;NA_Cost&#39; or &#39;PL_RealPriceGL&#39;.
    economicBucketComponent: "...",  // optional — Sub bucket of the economic bucket.
    economicBucketVariant: "...",  // optional — Categorisation of a Mark-to-market journal entry line into LongTerm or ShortTerm based on whether the ActivityDate is more than a year after the purchase trade date or not.
    levels: ,  // optional — Resolved data from the general ledger profile where the GeneralLedgerProfileCode is specified in the GetJournalEntryLines request body.
    sourceLevels: ,  // optional — Source data from the general ledger profile where the GeneralLedgerProfileCode is specified in the GetJournalEntryLines request body.
    movementSign: "...",  // optional — Indicates if the Journal Entry Line corresponds to a Long or Short movement.
    holdingSign: "...",  // optional — Indicates if the Journal Entry Line is operating against a Long or Short holding.
    ledgerColumn: "...",  // optional — Indicates if the Journal Entry Line is credit or debit.
    journalEntryLineType: "...",  // optional — Indicates the Journal Entry Line type
    shareClassBreakdowns: new List<JournalEntryLineShareClassBreakdown>(),  // optional — Share Class breakdown data for this Journal Entry Line.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundJournalEntryLine>(json);
```

- [ResourceId](ResourceId.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `SubHoldingKeys`
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [Property](Property.md) — used in `Properties`
- [JournalEntryLineShareClassBreakdown](JournalEntryLineShareClassBreakdown.md) — used in `ShareClassBreakdowns`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

