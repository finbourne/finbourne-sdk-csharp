# Finbourne.Sdk.Lusid.Model.WithholdingTaxValueSource

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Dimension** | **string** | Required | The name of the matching dimension this declaration populates, as it appears in the dataset field schema. A declaration naming a dimension neither dataset has is rejected. |
| **Source** | **string** | Required | The LUSID field the engine reads the dimension&#39;s value from, addressed in the same syntax used to filter results: a property key in the form Properties[{domain}/{scope}/{code}], such as Properties[Instrument/WithholdingTax/AssetClass] or Properties[Transaction/WithholdingTax/Custodian]; or the name of a field on the entity itself, such as Transaction.SettlementCurrency. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WithholdingTaxValueSource(
    dimension: "...",  // required — The name of the matching dimension this declaration populates, as it appears in the dataset field schema. A declaration naming a dimension neither dataset has is rejected.
    source: "..."  // required — The LUSID field the engine reads the dimension&#39;s value from, addressed in the same syntax used to filter results: a property key in the form Properties[{domain}/{scope}/{code}], such as Properties[Instrument/WithholdingTax/AssetClass] or Properties[Transaction/WithholdingTax/Custodian]; or the name of a field on the entity itself, such as Transaction.SettlementCurrency.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WithholdingTaxValueSource>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

