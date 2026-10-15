# Finbourne.Sdk.Lusid.Model.ManagementFeeTotals

The management fee totals over every partner.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Gross** | **decimal** | Required | The fee before offsets. |
| **Offset** | **decimal** | Required | The offset applied to the fee. |
| **Net** | **decimal** | Required | The fee after offsets. |
| **CarriedForward** | **decimal** | Required | Offset in excess of the fee, carried forward to the next period. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ManagementFeeTotals(
    gross: 0.0d,  // required — The fee before offsets.
    offset: 0.0d,  // required — The offset applied to the fee.
    net: 0.0d,  // required — The fee after offsets.
    carriedForward: 0.0d  // required — Offset in excess of the fee, carried forward to the next period.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ManagementFeeTotals>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

