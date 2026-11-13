# Finbourne.Sdk.Lusid.Model.TaxFundReconciliationProxyRow

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FundCode** | **string** | Optional | The code of the member fund. |
| **Amount** | **decimal** | Optional | The amount, in pounds. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxFundReconciliationProxyRow(
    fundCode: "...",  // optional — The code of the member fund.
    amount: 0.0d  // optional — The amount, in pounds.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxFundReconciliationProxyRow>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

