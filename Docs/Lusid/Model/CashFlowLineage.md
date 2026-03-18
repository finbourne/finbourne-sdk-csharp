# Finbourne.Sdk.Lusid.Model.CashFlowLineage

Lineage for cash flow value
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentType** | **string** | Optional | The instrument type of the instrument to which the cash flow belongs to. When upserting CashFlowValues, this  should be null. |
| **CashFlowType** | **string** | Optional | The cashflow type.When upserting CashFlowValues, this should be null, or one of [Unknown, Coupon, Notional,  Premium, Principal, Protection, Cash] |
| **InstrumentId** | **string** | Optional | The LUID of the instrument to which the cash flow belongs to. When upserting this should be null. |
| **LegId** | **string** | Optional | The leg id to which the cash flow belongs to. |
| **SourceTransactionId** | **string** | Optional | The source transaction of the instrument to which the cash flow belongs to. When upserting this should be null |
| **PayReceive** | **string** | Optional | Does the cash flow belong to the Pay or Receive leg. When upserting this should either be null or one of [Pay, Receive, NotApplicable] |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CashFlowLineage(
    instrumentType: "...",  // optional — The instrument type of the instrument to which the cash flow belongs to. When upserting CashFlowValues, this  should be null.
    cashFlowType: "...",  // optional — The cashflow type.When upserting CashFlowValues, this should be null, or one of [Unknown, Coupon, Notional,  Premium, Principal, Protection, Cash]
    instrumentId: "...",  // optional — The LUID of the instrument to which the cash flow belongs to. When upserting this should be null.
    legId: "...",  // optional — The leg id to which the cash flow belongs to.
    sourceTransactionId: "...",  // optional — The source transaction of the instrument to which the cash flow belongs to. When upserting this should be null
    payReceive: "..."  // optional — Does the cash flow belong to the Pay or Receive leg. When upserting this should either be null or one of [Pay, Receive, NotApplicable]
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CashFlowLineage>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

