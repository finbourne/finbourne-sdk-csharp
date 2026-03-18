# Finbourne.Sdk.Lusid.Model.Reconciliation

Representation of Reconciliation in LUSID Api
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ReconciliationId](ReconciliationId.md) | Optional | *No description available.* |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Name** | **string** | Optional | The name of the scheduled reconciliation |
| **Description** | **string** | Optional | A description of the scheduled reconciliation |
| **IsPortfolioGroup** | **bool** | Optional | Specifies whether reconciliation is between portfolios or portfolio groups |
| **Left** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Right** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Transactions** | [ReconciliationTransactions](ReconciliationTransactions.md) | Optional | *No description available.* |
| **Positions** | [ReconciliationConfiguration](ReconciliationConfiguration.md) | Optional | *No description available.* |
| **Valuations** | [ReconciliationConfiguration](ReconciliationConfiguration.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | Reconciliation properties |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Reconciliation(
    id: new ReconciliationId(...),  // optional
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    name: "...",  // optional — The name of the scheduled reconciliation
    description: "...",  // optional — A description of the scheduled reconciliation
    isPortfolioGroup: true,  // optional — Specifies whether reconciliation is between portfolios or portfolio groups
    left: new ResourceId(...),  // optional
    right: new ResourceId(...),  // optional
    transactions: new ReconciliationTransactions(...),  // optional
    positions: new ReconciliationConfiguration(...),  // optional
    valuations: new ReconciliationConfiguration(...),  // optional
    properties: new Property(...),  // optional — Reconciliation properties
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
var instance = JsonConvert.DeserializeObject<Reconciliation>(json);
```


## Related Models

- [ReconciliationId](ReconciliationId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ReconciliationTransactions](ReconciliationTransactions.md)
- [ReconciliationConfiguration](ReconciliationConfiguration.md)
- [ReconciliationConfiguration](ReconciliationConfiguration.md)
- [Property](Property.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

