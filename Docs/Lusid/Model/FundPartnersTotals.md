# Finbourne.Sdk.Lusid.Model.FundPartnersTotals

Totals across every register line of the fund, independent of paging. Commitments are totalled per commitment  currency; amounts in different currencies are never added together.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CommittedByCurrency** | **Dictionary&lt;string, decimal&gt;** | Required | The total committed capital across all partners, per commitment currency, keyed by currency code. Commitments in different currencies are not added together. |
| **PartnerCount** | **int** | Required | The number of partners (register lines) in the fund. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundPartnersTotals(
    committedByCurrency: ,  // required — The total committed capital across all partners, per commitment currency, keyed by currency code. Commitments in different currencies are not added together.
    partnerCount: 0  // required — The number of partners (register lines) in the fund.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundPartnersTotals>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

