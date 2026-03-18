# Finbourne.Sdk.Lusid.Model.GroupReconciliationDefinitionPortfolioEntityIds

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | [List&lt;PortfolioEntityId&gt;](PortfolioEntityId.md) | Required | Portfolio Entity Id of the left side of a reconciliation |
| **Right** | [List&lt;PortfolioEntityId&gt;](PortfolioEntityId.md) | Required | Portfolio Entity Id of the right side of a reconciliation |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationDefinitionPortfolioEntityIds(
    left: new List<PortfolioEntityId>(),  // required — Portfolio Entity Id of the left side of a reconciliation
    right: new List<PortfolioEntityId>()  // required — Portfolio Entity Id of the right side of a reconciliation
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationDefinitionPortfolioEntityIds>(json);
```


## Related Models

- [PortfolioEntityId](PortfolioEntityId.md) — used in `Left`
- [PortfolioEntityId](PortfolioEntityId.md) — used in `Right`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

