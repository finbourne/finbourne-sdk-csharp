# Finbourne.Sdk.Lusid.Model.AggregatedTransactionsRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FromTransactionDate** | **DateTimeOffset** | Required | *No description available.* |
| **ToTransactionDate** | **DateTimeOffset** | Required | *No description available.* |
| **PortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **PortfolioEntityIds** | [List&lt;PortfolioEntityId&gt;](PortfolioEntityId.md) | Optional | The set of portfolio or portfolio group identifiers containing the relevant transactions. |
| **AsAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **Metrics** | [List&lt;AggregateSpec&gt;](AggregateSpec.md) | Required | *No description available.* |
| **GroupBy** | **List&lt;string&gt;** | Optional | *No description available.* |
| **Filters** | [List&lt;PropertyFilter&gt;](PropertyFilter.md) | Optional | *No description available.* |
| **Sort** | [List&lt;OrderBySpec&gt;](OrderBySpec.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AggregatedTransactionsRequest(
    fromTransactionDate: DateTimeOffset.Now,  // required
    toTransactionDate: DateTimeOffset.Now,  // required
    portfolioId: new ResourceId(...),  // optional
    portfolioEntityIds: new List<PortfolioEntityId>(),  // optional — The set of portfolio or portfolio group identifiers containing the relevant transactions.
    asAt: DateTimeOffset.Now,  // optional
    metrics: new List<AggregateSpec>(),  // required
    groupBy: ,  // optional
    filters: new List<PropertyFilter>(),  // optional
    sort: new List<OrderBySpec>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AggregatedTransactionsRequest>(json);
```

- [ResourceId](ResourceId.md)
- [PortfolioEntityId](PortfolioEntityId.md) — used in `PortfolioEntityIds`
- [AggregateSpec](AggregateSpec.md)
- [PropertyFilter](PropertyFilter.md)
- [OrderBySpec](OrderBySpec.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

