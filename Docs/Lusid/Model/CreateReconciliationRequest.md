# Finbourne.Sdk.Lusid.Model.CreateReconciliationRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The unique identifier associated with the reconciliation |
| **Name** | **string** | Optional | The name of the scheduled reconciliation |
| **Description** | **string** | Optional | A description of the scheduled reconciliation |
| **IsPortfolioGroup** | **bool** | Optional | Specifies whether reconciliation is between portfolios or portfolio groups |
| **Left** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Right** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Transactions** | [ReconciliationTransactions](ReconciliationTransactions.md) | Optional | *No description available.* |
| **Positions** | [ReconciliationConfiguration](ReconciliationConfiguration.md) | Optional | *No description available.* |
| **Valuations** | [ReconciliationConfiguration](ReconciliationConfiguration.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | Reconciliation properties |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateReconciliationRequest(
    code: "...",  // required — The unique identifier associated with the reconciliation
    name: "...",  // optional — The name of the scheduled reconciliation
    description: "...",  // optional — A description of the scheduled reconciliation
    isPortfolioGroup: true,  // optional — Specifies whether reconciliation is between portfolios or portfolio groups
    left: new ResourceId(...),  // optional
    right: new ResourceId(...),  // optional
    transactions: new ReconciliationTransactions(...),  // optional
    positions: new ReconciliationConfiguration(...),  // optional
    valuations: new ReconciliationConfiguration(...),  // optional
    properties: new Property(...)  // optional — Reconciliation properties
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateReconciliationRequest>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ReconciliationTransactions](ReconciliationTransactions.md)
- [ReconciliationConfiguration](ReconciliationConfiguration.md)
- [ReconciliationConfiguration](ReconciliationConfiguration.md)
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

