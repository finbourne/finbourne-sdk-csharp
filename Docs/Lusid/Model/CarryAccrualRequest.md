# Finbourne.Sdk.Lusid.Model.CarryAccrualRequest

The request to accrue carried interest on a partnership fund from amounts a waterfall has produced.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PeriodEnd** | **DateTimeOffset** | Required | The date carry is accrued to. |
| **Source** | **string** | Required | The waterfall or model the carry amounts came from. |
| **Amounts** | [List&lt;CarryAccrualAmount&gt;](CarryAccrualAmount.md) | Required | The carry each partner has earned to the period end, as the source states it. |
| **Book** | **bool** | Optional | When true, the accrual deltas are booked. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CarryAccrualRequest(
    periodEnd: DateTimeOffset.Now,  // required — The date carry is accrued to.
    source: "...",  // required — The waterfall or model the carry amounts came from.
    amounts: new List<CarryAccrualAmount>(),  // required — The carry each partner has earned to the period end, as the source states it.
    book: true  // optional — When true, the accrual deltas are booked.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CarryAccrualRequest>(json);
```

- [CarryAccrualAmount](CarryAccrualAmount.md) — used in `Amounts`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

