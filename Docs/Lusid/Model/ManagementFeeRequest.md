# Finbourne.Sdk.Lusid.Model.ManagementFeeRequest

The request to calculate a period's management fee for the partners of a partnership fund.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PeriodStart** | **DateTimeOffset** | Required | The start of the fee period, exclusive. |
| **PeriodEnd** | **DateTimeOffset** | Required | The end of the fee period, inclusive. |
| **Basis** | **string** | Optional | The capital base the fee is charged on. Available values: Auto, CommittedCapital, InvestedCapital. Auto charges on committed capital until the investment period ends and on invested capital after. |
| **Offsets** | [List&lt;ManagementFeeOffset&gt;](ManagementFeeOffset.md) | Optional | Fee income received by the manager that offsets the management fee. |
| **Book** | **bool** | Optional | When true, the net fee per partner is booked. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ManagementFeeRequest(
    periodStart: DateTimeOffset.Now,  // required — The start of the fee period, exclusive.
    periodEnd: DateTimeOffset.Now,  // required — The end of the fee period, inclusive.
    basis: "...",  // optional — The capital base the fee is charged on. Available values: Auto, CommittedCapital, InvestedCapital. Auto charges on committed capital until the investment period ends and on invested capital after.
    offsets: new List<ManagementFeeOffset>(),  // optional — Fee income received by the manager that offsets the management fee.
    book: true  // optional — When true, the net fee per partner is booked.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ManagementFeeRequest>(json);
```

- [ManagementFeeOffset](ManagementFeeOffset.md) — used in `Offsets`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

