# Finbourne.Sdk.Lusid.Model.TaxSyncStatus

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Portfolios** | [List&lt;TaxPortfolioSyncStatus&gt;](TaxPortfolioSyncStatus.md) | Required | The sync position of each portfolio in the Fund. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxSyncStatus(
    portfolios: new List<TaxPortfolioSyncStatus>()  // required — The sync position of each portfolio in the Fund.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxSyncStatus>(json);
```


## Related Models

- [TaxPortfolioSyncStatus](TaxPortfolioSyncStatus.md) — used in `Portfolios`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

