# Finbourne.Sdk.Lusid.Model.RecLinkedResult

A rec result of a different rec type in the same rec instance whose items share an identifier with this  result's items, and the keys that established the link. Links are symmetric: the linked result carries one back.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | The id of the linked result within the same run, as carried in that result&#39;s own id field, e.g. &#39;break-3&#39;. With recType, names the result uniquely. |
| **RecType** | **string** | Required | The rec type of the linked result. Always differs from this result&#39;s rec type. Available values: Holding, CashHolding, Valuation, InputTransaction, OutputTransaction, SettlementActivity, External, Instrument. |
| **LinkedBy** | [RecLinkedBy](RecLinkedBy.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecLinkedResult(
    id: "...",  // required — The id of the linked result within the same run, as carried in that result&#39;s own id field, e.g. &#39;break-3&#39;. With recType, names the result uniquely.
    recType: "...",  // required — The rec type of the linked result. Always differs from this result&#39;s rec type. Available values: Holding, CashHolding, Valuation, InputTransaction, OutputTransaction, SettlementActivity, External, Instrument.
    linkedBy: new RecLinkedBy(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecLinkedResult>(json);
```

- [RecLinkedBy](RecLinkedBy.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

