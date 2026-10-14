# Finbourne.Sdk.Lusid.Model.AllocationEventEqualisationFeeCatchUp

The management fees one admitted partner owes from the first fee date to the close, as an explicit amount.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Required | The admitted partner the fee catch-up is charged to. |
| **Amount** | **decimal** | Required | The fee catch-up in the event currency. Must not be negative. |
| **DueDate** | **DateTimeOffset?** | Optional | The date the fee would have been due had the partner been admitted at the first close, from which interest on it accrues when charged. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventEqualisationFeeCatchUp(
    investorRecordId: "...",  // required — The admitted partner the fee catch-up is charged to.
    amount: 0.0d,  // required — The fee catch-up in the event currency. Must not be negative.
    dueDate: DateTimeOffset.Now  // optional — The date the fee would have been due had the partner been admitted at the first close, from which interest on it accrues when charged.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventEqualisationFeeCatchUp>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

