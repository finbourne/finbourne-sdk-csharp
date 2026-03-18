# Finbourne.Sdk.Lusid.Model.BatchUpsertPortfolioTransactionsResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [Dictionary&lt;string, Transaction&gt;](Transaction.md) | Optional | The transactions which have been successfully upserted. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The transactions that could not be upserted along with a reason for their failure. |
| **Metadata** | **Dictionary&lt;string, List&lt;ResponseMetaData&gt;&gt;** | Optional | Contains warnings related to unresolved instruments or non-existent transaction types for the upserted trades |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchUpsertPortfolioTransactionsResponse(
    values: new Transaction(...),  // optional — The transactions which have been successfully upserted.
    failed: new ErrorDetail(...),  // optional — The transactions that could not be upserted along with a reason for their failure.
    metadata: ,  // optional — Contains warnings related to unresolved instruments or non-existent transaction types for the upserted trades
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchUpsertPortfolioTransactionsResponse>(json);
```


## Related Models

- [Transaction](Transaction.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

