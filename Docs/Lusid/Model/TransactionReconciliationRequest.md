# Finbourne.Sdk.Lusid.Model.TransactionReconciliationRequest

Specifies the parameter to be use when performing a Transaction Reconciliation.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LeftPortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **RightPortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **MappingId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **FromTransactionDate** | **DateTimeOffset** | Required | *No description available.* |
| **ToTransactionDate** | **DateTimeOffset** | Required | *No description available.* |
| **AsAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **PropertyKeys** | **List&lt;string&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionReconciliationRequest(
    leftPortfolioId: new ResourceId(...),  // required
    rightPortfolioId: new ResourceId(...),  // required
    mappingId: new ResourceId(...),  // optional
    fromTransactionDate: DateTimeOffset.Now,  // required
    toTransactionDate: DateTimeOffset.Now,  // required
    asAt: DateTimeOffset.Now,  // optional
    propertyKeys:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionReconciliationRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

