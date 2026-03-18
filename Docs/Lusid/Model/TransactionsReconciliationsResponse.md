# Finbourne.Sdk.Lusid.Model.TransactionsReconciliationsResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Mapping** | [Mapping](Mapping.md) | Optional | *No description available.* |
| **Data** | [List&lt;ReconciledTransaction&gt;](ReconciledTransaction.md) | Optional | The result of this reconciliation |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionsReconciliationsResponse(
    mapping: new Mapping(...),  // optional
    data: new List<ReconciledTransaction>()  // optional — The result of this reconciliation
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionsReconciliationsResponse>(json);
```


## Related Models

- [Mapping](Mapping.md)
- [ReconciledTransaction](ReconciledTransaction.md) — used in `Data`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

