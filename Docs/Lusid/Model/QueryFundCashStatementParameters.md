# Finbourne.Sdk.Lusid.Model.QueryFundCashStatementParameters

Request body for querying a Fund Cash Statement.  Extends the diary entry query pattern with cash statement display mode.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Start** | [DateOrDiaryEntry](DateOrDiaryEntry.md) | Optional | *No description available.* |
| **End** | [DateOrDiaryEntry](DateOrDiaryEntry.md) | Required | *No description available.* |
| **Variant** | **string** | Optional | Optional diary entry variant (e.g. for multi-estimate scenarios). |
| **DisplayMode** | **string** | Optional | Cash statement display mode: ShowReversal (default) shows full reversal/TrueUp detail; Consolidated collapses reversals into AvgRateCorrection rows. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QueryFundCashStatementParameters(
    start: new DateOrDiaryEntry(...),  // optional
    end: new DateOrDiaryEntry(...),  // required
    variant: "...",  // optional — Optional diary entry variant (e.g. for multi-estimate scenarios).
    displayMode: "..."  // optional — Cash statement display mode: ShowReversal (default) shows full reversal/TrueUp detail; Consolidated collapses reversals into AvgRateCorrection rows.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QueryFundCashStatementParameters>(json);
```


## Related Models

- [DateOrDiaryEntry](DateOrDiaryEntry.md)
- [DateOrDiaryEntry](DateOrDiaryEntry.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

