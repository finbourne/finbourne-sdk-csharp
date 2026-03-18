# Finbourne.Sdk.Lusid.Model.PnlJournalEntryLine

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PnlBucket** | **string** | Optional | The Filter ID of the grouping used from the Fund Configuration PnL filters |
| **JournalEntryLine** | [JournalEntryLine](JournalEntryLine.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PnlJournalEntryLine(
    pnlBucket: "...",  // optional — The Filter ID of the grouping used from the Fund Configuration PnL filters
    journalEntryLine: new JournalEntryLine(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PnlJournalEntryLine>(json);
```

- [JournalEntryLine](JournalEntryLine.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

