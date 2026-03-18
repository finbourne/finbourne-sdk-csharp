# Finbourne.Sdk.Lusid.Model.FeeRule

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | *No description available.* |
| **TransactionPropertyKey** | **string** | Required | *No description available.* |
| **TransactionType** | **string** | Required | *No description available.* |
| **Country** | **string** | Required | *No description available.* |
| **Counterparty** | **string** | Required | *No description available.* |
| **TransactionCurrency** | **string** | Required | *No description available.* |
| **SettlementCurrency** | **string** | Required | *No description available.* |
| **ExecutionBroker** | **string** | Required | *No description available.* |
| **Custodian** | **string** | Required | *No description available.* |
| **Exchange** | **string** | Required | *No description available.* |
| **Fee** | [CalculationInfo](CalculationInfo.md) | Required | *No description available.* |
| **MinFee** | [CalculationInfo](CalculationInfo.md) | Optional | *No description available.* |
| **MaxFee** | [CalculationInfo](CalculationInfo.md) | Optional | *No description available.* |
| **AdditionalKeys** | **Dictionary&lt;string, string&gt;** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FeeRule(
    code: "...",  // required
    transactionPropertyKey: "...",  // required
    transactionType: "...",  // required
    country: "...",  // required
    counterparty: "...",  // required
    transactionCurrency: "...",  // required
    settlementCurrency: "...",  // required
    executionBroker: "...",  // required
    custodian: "...",  // required
    exchange: "...",  // required
    fee: new CalculationInfo(...),  // required
    minFee: new CalculationInfo(...),  // optional
    maxFee: new CalculationInfo(...),  // optional
    additionalKeys: ,  // optional
    description: "...",  // optional
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FeeRule>(json);
```

- [CalculationInfo](CalculationInfo.md)
- [CalculationInfo](CalculationInfo.md)
- [CalculationInfo](CalculationInfo.md)
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

