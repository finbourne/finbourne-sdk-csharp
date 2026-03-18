# Finbourne.Sdk.Lusid.Model.TransactionQueryParameters

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Required | The lower bound effective datetime or cut label (inclusive) from which to build the transactions. |
| **EndDate** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Required | The upper bound effective datetime or cut label (inclusive) from which to retrieve transactions. |
| **QueryMode** | **string** | Optional | The date to compare against the upper and lower bounds for the effective datetime or cut label. Defaults to &#39;TradeDate&#39; if not specified. The available values are: TradeDate, SettleDate |
| **ShowCancelledTransactions** | **bool** | Optional | Option to specify whether or not to include cancelled transactions in the output. Defaults to False if not specified. |
| **TimelineScope** | **string** | Optional | Scope of the Timeline for the Portfolio. The Timeline to be used while building transactions |
| **TimelineCode** | **string** | Optional | Code of the Timeline for the Portfolio. The Timeline to be used while building transactions. This can optionally include a colon, followed by the Closed Period Id to use at the head of the timeline, for a timeline with unconfirmed periods. |
| **IncludeEconomics** | **bool** | Optional | By default is false. When set to true the Economics data would be populated in the response. |
| **IncludeSettlementStatus** | **bool** | Optional | By default is false. When set to true the Settlement Status data would be populated in the response. |
| **SettlementStatusDate** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | Optional date used to specify end of an extended window for settlement information. When provided, transactions will be returned between start and end date, but settlement information between start date and this date will be included. When provided, the value must be greater than or equal to end date. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionQueryParameters(
    startDate: new DateTimeOrCutLabel(...),  // required — The lower bound effective datetime or cut label (inclusive) from which to build the transactions.
    endDate: new DateTimeOrCutLabel(...),  // required — The upper bound effective datetime or cut label (inclusive) from which to retrieve transactions.
    queryMode: "...",  // optional — The date to compare against the upper and lower bounds for the effective datetime or cut label. Defaults to &#39;TradeDate&#39; if not specified. The available values are: TradeDate, SettleDate
    showCancelledTransactions: true,  // optional — Option to specify whether or not to include cancelled transactions in the output. Defaults to False if not specified.
    timelineScope: "...",  // optional — Scope of the Timeline for the Portfolio. The Timeline to be used while building transactions
    timelineCode: "...",  // optional — Code of the Timeline for the Portfolio. The Timeline to be used while building transactions. This can optionally include a colon, followed by the Closed Period Id to use at the head of the timeline, for a timeline with unconfirmed periods.
    includeEconomics: true,  // optional — By default is false. When set to true the Economics data would be populated in the response.
    includeSettlementStatus: true,  // optional — By default is false. When set to true the Settlement Status data would be populated in the response.
    settlementStatusDate: new DateTimeOrCutLabel(...)  // optional — Optional date used to specify end of an extended window for settlement information. When provided, transactions will be returned between start and end date, but settlement information between start date and this date will be included. When provided, the value must be greater than or equal to end date.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionQueryParameters>(json);
```


## Related Models

- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `StartDate`
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EndDate`
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `SettlementStatusDate`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

