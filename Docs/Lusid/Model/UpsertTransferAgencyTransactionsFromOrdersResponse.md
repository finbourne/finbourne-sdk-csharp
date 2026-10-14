# Finbourne.Sdk.Lusid.Model.UpsertTransferAgencyTransactionsFromOrdersResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Successes** | [Dictionary&lt;string, TransferAgencyTransactionFromOrderResult&gt;](TransferAgencyTransactionFromOrderResult.md) | Optional | A dictionary of successfully priced orders, keyed by the request key. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | A dictionary of failed order pricing attempts, keyed by the request key, containing error details. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertTransferAgencyTransactionsFromOrdersResponse(
    successes: new TransferAgencyTransactionFromOrderResult(...),  // optional — A dictionary of successfully priced orders, keyed by the request key.
    failed: new ErrorDetail(...),  // optional — A dictionary of failed order pricing attempts, keyed by the request key, containing error details.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertTransferAgencyTransactionsFromOrdersResponse>(json);
```


## Related Models

- [TransferAgencyTransactionFromOrderResult](TransferAgencyTransactionFromOrderResult.md) — used in `Successes`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

