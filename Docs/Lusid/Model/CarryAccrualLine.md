# Finbourne.Sdk.Lusid.Model.CarryAccrualLine

One partner's line on a carry accrual.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Required | The investor record the amount belongs to. |
| **PreviousCarryToDate** | **decimal** | Required | The cumulative carry already on the books for the partner. |
| **CarryToDate** | **decimal** | Required | The cumulative carry the partner has earned to the period end. |
| **Delta** | **decimal** | Required | The accrual booked: the carry to date less what was already on the books. |
| **ClawbackExposure** | **decimal** | Required | The carry that would have to be returned if the fund liquidated at the period end. |
| **Status** | **string** | Required | What happened to the line. Available values: Unchanged, Accrued, Released. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CarryAccrualLine(
    investorRecordId: "...",  // required — The investor record the amount belongs to.
    previousCarryToDate: 0.0d,  // required — The cumulative carry already on the books for the partner.
    carryToDate: 0.0d,  // required — The cumulative carry the partner has earned to the period end.
    delta: 0.0d,  // required — The accrual booked: the carry to date less what was already on the books.
    clawbackExposure: 0.0d,  // required — The carry that would have to be returned if the fund liquidated at the period end.
    status: "..."  // required — What happened to the line. Available values: Unchanged, Accrued, Released.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CarryAccrualLine>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

