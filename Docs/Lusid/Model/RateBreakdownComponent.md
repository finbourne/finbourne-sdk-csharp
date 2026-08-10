# Finbourne.Sdk.Lusid.Model.RateBreakdownComponent

A tax-characterised payout line within a CashElection on a CashDividendEvent.  Each line carries a rate-type classifier and a per-unit amount in the parent election's currency.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RateType** | **string** | Required | Free-string distribution rate-type code (e.g. UNFR, FLFR, PID). |
| **DividendRate** | **decimal** | Required | Per-unit amount for this line, in the parent election&#39;s dividend currency. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RateBreakdownComponent(
    rateType: "...",  // required — Free-string distribution rate-type code (e.g. UNFR, FLFR, PID).
    dividendRate: 0.0d  // required — Per-unit amount for this line, in the parent election&#39;s dividend currency.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RateBreakdownComponent>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

