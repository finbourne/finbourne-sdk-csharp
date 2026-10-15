# Finbourne.Sdk.Lusid.Model.ManagementFeeLine

One partner's management fee for the period.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Required | The investor record the fee belongs to. |
| **BasisAmount** | **decimal** | Required | The capital the fee was charged on. |
| **Rate** | **decimal** | Required | The annual fee rate applied. |
| **DayCountFraction** | **decimal** | Required | The fraction of a year the period covers, on an ACT/365 basis. |
| **Gross** | **decimal** | Required | The fee before offsets. |
| **Offset** | **decimal** | Required | The offset applied to the fee. |
| **Net** | **decimal** | Required | The fee after offsets. |
| **CarriedForward** | **decimal** | Required | Offset in excess of the fee, carried forward to the next period. |
| **Waived** | **bool** | Required | Whether the partner is fee-exempt and the fee was waived. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ManagementFeeLine(
    investorRecordId: "...",  // required — The investor record the fee belongs to.
    basisAmount: 0.0d,  // required — The capital the fee was charged on.
    rate: 0.0d,  // required — The annual fee rate applied.
    dayCountFraction: 0.0d,  // required — The fraction of a year the period covers, on an ACT/365 basis.
    gross: 0.0d,  // required — The fee before offsets.
    offset: 0.0d,  // required — The offset applied to the fee.
    net: 0.0d,  // required — The fee after offsets.
    carriedForward: 0.0d,  // required — Offset in excess of the fee, carried forward to the next period.
    waived: true  // required — Whether the partner is fee-exempt and the fee was waived.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ManagementFeeLine>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

