# Finbourne.Sdk.Lusid.Model.DealingLineNotValued

A dealing line read for a swing decision that could not be valued into its share class currency, and why.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OrderId** | **string** | Required | The identifier of the dealing order that could not be valued, as scope/code. |
| **ShareClass** | **string** | Optional | The share class the order deals in, keyed as the valuation point&#39;s share classes are. |
| **Currency** | **string** | Optional | The currency the order&#39;s amount is in. Absent when the line carries no amount. |
| **Reason** | **string** | Required | Why the line could not be valued into the share class currency. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DealingLineNotValued(
    orderId: "...",  // required — The identifier of the dealing order that could not be valued, as scope/code.
    shareClass: "...",  // optional — The share class the order deals in, keyed as the valuation point&#39;s share classes are.
    currency: "...",  // optional — The currency the order&#39;s amount is in. Absent when the line carries no amount.
    reason: "..."  // required — Why the line could not be valued into the share class currency.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DealingLineNotValued>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

