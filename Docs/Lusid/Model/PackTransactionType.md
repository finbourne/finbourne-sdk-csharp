# Finbourne.Sdk.Lusid.Model.PackTransactionType

A transaction type carried by a partnership configuration pack.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The transaction type. |
| **Description** | **string** | Optional | A description of the transaction type. |
| **DebitAccount** | **string** | Required | The account debited. |
| **CreditAccount** | **string** | Required | The account credited. |
| **Direction** | **string** | Required | The direction of the capital movement from the partner&#39;s point of view. Available values: Inflow, Outflow, Neutral. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PackTransactionType(
    type: "...",  // required — The transaction type.
    description: "...",  // optional — A description of the transaction type.
    debitAccount: "...",  // required — The account debited.
    creditAccount: "...",  // required — The account credited.
    direction: "..."  // required — The direction of the capital movement from the partner&#39;s point of view. Available values: Inflow, Outflow, Neutral.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PackTransactionType>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

