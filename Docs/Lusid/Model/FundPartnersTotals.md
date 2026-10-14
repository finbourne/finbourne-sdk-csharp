# Finbourne.Sdk.Lusid.Model.FundPartnersTotals

Totals across every register line of the fund, independent of paging.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Committed** | **decimal** | Required | The total committed capital across all partners. |
| **PartnerCount** | **int** | Required | The number of partners (register lines) in the fund. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundPartnersTotals(
    committed: 0.0d,  // required — The total committed capital across all partners.
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

