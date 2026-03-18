# Finbourne.Sdk.Lusid.Model.TargetTaxLotRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Units** | **decimal** | Required | The number of units of the instrument in this tax-lot. |
| **Cost** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **PortfolioCost** | **decimal?** | Optional | The total cost of the tax-lot in the transaction portfolio&#39;s base currency. |
| **Price** | **decimal?** | Optional | The purchase price of each unit of the instrument held in this tax-lot. This forms part of the unique key required for multiple tax-lots. |
| **PurchaseDate** | **DateTimeOffset?** | Optional | The purchase date of this tax-lot. This forms part of the unique key required for multiple tax-lots. |
| **SettlementDate** | **DateTimeOffset?** | Optional | The settlement date of the tax-lot&#39;s opening transaction. |
| **NotionalCost** | **decimal?** | Optional | The notional cost of the tax-lot&#39;s opening transaction. |
| **VariationMargin** | **decimal?** | Optional | The variation margin of the tax-lot&#39;s opening transaction. |
| **VariationMarginPortfolioCcy** | **decimal?** | Optional | The variation margin in portfolio currency of the tax-lot&#39;s opening transaction. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TargetTaxLotRequest(
    units: 0.0d,  // required — The number of units of the instrument in this tax-lot.
    cost: new CurrencyAndAmount(...),  // optional
    portfolioCost: 0.0d,  // optional — The total cost of the tax-lot in the transaction portfolio&#39;s base currency.
    price: 0.0d,  // optional — The purchase price of each unit of the instrument held in this tax-lot. This forms part of the unique key required for multiple tax-lots.
    purchaseDate: DateTimeOffset.Now,  // optional — The purchase date of this tax-lot. This forms part of the unique key required for multiple tax-lots.
    settlementDate: DateTimeOffset.Now,  // optional — The settlement date of the tax-lot&#39;s opening transaction.
    notionalCost: 0.0d,  // optional — The notional cost of the tax-lot&#39;s opening transaction.
    variationMargin: 0.0d,  // optional — The variation margin of the tax-lot&#39;s opening transaction.
    variationMarginPortfolioCcy: 0.0d  // optional — The variation margin in portfolio currency of the tax-lot&#39;s opening transaction.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TargetTaxLotRequest>(json);
```

- [CurrencyAndAmount](CurrencyAndAmount.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

