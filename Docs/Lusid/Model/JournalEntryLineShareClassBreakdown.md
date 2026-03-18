# Finbourne.Sdk.Lusid.Model.JournalEntryLineShareClassBreakdown

The apportionment from overall fund level journal entry Line to the share class.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ShortCode** | **string** | Optional | The share class identifier. |
| **ApportionmentFactor** | **decimal** | Optional | The share class apportionment factor (capital ratio). |
| **LocalValue** | **decimal** | Optional | This journal entry line&#39;s local value amount after apportionment is applied. |
| **BaseValue** | **decimal** | Optional | This journal entry line&#39;s base value amount after apportionment is applied |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new JournalEntryLineShareClassBreakdown(
    shortCode: "...",  // optional — The share class identifier.
    apportionmentFactor: 0.0d,  // optional — The share class apportionment factor (capital ratio).
    localValue: 0.0d,  // optional — This journal entry line&#39;s local value amount after apportionment is applied.
    baseValue: 0.0d  // optional — This journal entry line&#39;s base value amount after apportionment is applied
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<JournalEntryLineShareClassBreakdown>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

