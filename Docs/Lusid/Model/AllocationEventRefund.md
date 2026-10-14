# Finbourne.Sdk.Lusid.Model.AllocationEventRefund

Cash the fund owes back to an investor record.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Optional | The investor record the refund is owed to. |
| **Amount** | **decimal** | Optional | The amount owed back, in the event currency. |
| **Reason** | **string** | Optional | Why the refund arose: Overpayment or Reversal. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventRefund(
    investorRecordId: "...",  // optional — The investor record the refund is owed to.
    amount: 0.0d,  // optional — The amount owed back, in the event currency.
    reason: "..."  // optional — Why the refund arose: Overpayment or Reversal.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventRefund>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

