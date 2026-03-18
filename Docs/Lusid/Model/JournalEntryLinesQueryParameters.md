# Finbourne.Sdk.Lusid.Model.JournalEntryLinesQueryParameters

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Start** | [DateOrDiaryEntry](DateOrDiaryEntry.md) | Optional | *No description available.* |
| **End** | [DateOrDiaryEntry](DateOrDiaryEntry.md) | Optional | *No description available.* |
| **Variant** | **string** | Optional | Unique Variant for the given Valuation points. If not provided, defaults to empty string. |
| **DateMode** | **string** | Optional | The mode of calculation of the journal entry lines. The available values are: ActivityDate, AccountingDate. |
| **GeneralLedgerProfileCode** | **string** | Optional | The optional code of a general ledger profile used to decorate journal entry lines with levels. |
| **PropertyKeys** | **List&lt;string&gt;** | Optional | A list of property keys from the &#39;Instrument&#39;, &#39;Transaction&#39;, &#39;Portfolio&#39;, &#39;Account&#39;, &#39;LegalEntity&#39; or &#39;CustodianAccount&#39; domain to decorate onto the journal entry lines. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new JournalEntryLinesQueryParameters(
    start: new DateOrDiaryEntry(...),  // optional
    end: new DateOrDiaryEntry(...),  // optional
    variant: "...",  // optional — Unique Variant for the given Valuation points. If not provided, defaults to empty string.
    dateMode: "...",  // optional — The mode of calculation of the journal entry lines. The available values are: ActivityDate, AccountingDate.
    generalLedgerProfileCode: "...",  // optional — The optional code of a general ledger profile used to decorate journal entry lines with levels.
    propertyKeys:   // optional — A list of property keys from the &#39;Instrument&#39;, &#39;Transaction&#39;, &#39;Portfolio&#39;, &#39;Account&#39;, &#39;LegalEntity&#39; or &#39;CustodianAccount&#39; domain to decorate onto the journal entry lines.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<JournalEntryLinesQueryParameters>(json);
```


## Related Models

- [DateOrDiaryEntry](DateOrDiaryEntry.md)
- [DateOrDiaryEntry](DateOrDiaryEntry.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

