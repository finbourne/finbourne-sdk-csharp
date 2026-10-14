# Finbourne.Sdk.Lusid.Model.AllocationReceivable

One investor's position on a booked capital call.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Optional | The investor record. |
| **Called** | **decimal** | Optional | What the investor record was called for. |
| **Received** | **decimal** | Optional | What has been received and applied so far. |
| **Outstanding** | **decimal** | Optional | What is still owed. Never negative: an overpayment becomes a refund payable instead. |
| **DaysPastDue** | **int** | Optional | How many days past the due date the outstanding amount is, or zero when not yet due or nothing is owed. |
| **Bucket** | **string** | Optional | The ageing bucket: Current, 1-30, 31-60, 61-90 or 90+. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationReceivable(
    investorRecordId: "...",  // optional — The investor record.
    called: 0.0d,  // optional — What the investor record was called for.
    received: 0.0d,  // optional — What has been received and applied so far.
    outstanding: 0.0d,  // optional — What is still owed. Never negative: an overpayment becomes a refund payable instead.
    daysPastDue: 0,  // optional — How many days past the due date the outstanding amount is, or zero when not yet due or nothing is owed.
    bucket: "..."  // optional — The ageing bucket: Current, 1-30, 31-60, 61-90 or 90+.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationReceivable>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

