# Finbourne.Sdk.Lusid.Model.AdjustmentEntryResponse

A single adjustments entry on a virtual transaction override record: the fields it changes and its status.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Adjustment** | [AdjustmentDefinitionResponse](AdjustmentDefinitionResponse.md) | Optional | *No description available.* |
| **Status** | **string** | Optional | Whether this entry&#39;s target virtual transaction id still matches one the event currently generates. Available values: Applied, Orphaned, Superseded. |
| **VirtualTransactionId** | **string** | Optional | The id of the virtual transaction this entry targets, as it appears in the requested portfolio. Null when the entry targets no virtual transaction the requested portfolio currently generates. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AdjustmentEntryResponse(
    adjustment: new AdjustmentDefinitionResponse(...),  // optional
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
var instance = JsonConvert.DeserializeObject<AdjustmentEntryResponse>(json);
```


## Related Models

- [AdjustmentDefinitionResponse](AdjustmentDefinitionResponse.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

