# Finbourne.Sdk.Lusid.Model.OverrideEntryResponse

A single overrides entry on a virtual transaction override record: the replacement transaction(s) that  stand in for the overridden virtual transaction, plus its status and diagnostics.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Replacements** | [List&lt;OverrideDefinitionResponse&gt;](OverrideDefinitionResponse.md) | Optional | The replacement transactions that stand in for the overridden virtual transaction. |
| **Status** | **string** | Optional | Whether this entry&#39;s target virtual transaction id still matches one the event currently generates. Available values: Applied, Orphaned, Superseded. |
| **VirtualTransactionId** | **string** | Optional | The id of the virtual transaction this entry targets, as it appears in the requested portfolio. Null when the entry targets no virtual transaction the requested portfolio currently generates. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OverrideEntryResponse(
    replacements: new List<OverrideDefinitionResponse>(),  // optional — The replacement transactions that stand in for the overridden virtual transaction.
    status: "...",  // optional — Whether this entry&#39;s target virtual transaction id still matches one the event currently generates. Available values: Applied, Orphaned, Superseded.
    virtualTransactionId: "..."  // optional — The id of the virtual transaction this entry targets, as it appears in the requested portfolio. Null when the entry targets no virtual transaction the requested portfolio currently generates.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OverrideEntryResponse>(json);
```


## Related Models

- [OverrideDefinitionResponse](OverrideDefinitionResponse.md) — used in `Replacements`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

