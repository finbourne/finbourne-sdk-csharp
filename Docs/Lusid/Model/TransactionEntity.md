# Finbourne.Sdk.Lusid.Model.TransactionEntity

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Required | The link to the transaction entity. |
| **EntityUniqueId** | **string** | Required | The unique id of the transaction, combining the portfolio and transaction identifiers. |
| **AsAtVersionNumber** | **int?** | Optional | The version number of the transaction entity at the requested asAt. |
| **Status** | **string** | Required | The status of the transaction entity. &#39;Prevailing&#39; when the transaction exists — including a cancelled transaction, whose cancellation is reflected in its own status rather than here; &#39;Deleted&#39; when the transaction&#39;s portfolio has been deleted; &#39;DoesNotExist&#39; when the transaction does not yet exist (e.g. staged creation preview). Available values: Prevailing, Deleted, DoesNotExist. |
| **AsAtDeleted** | **DateTimeOffset?** | Optional | The asAt datetime at which the portfolio (and by extension, the transaction) was deleted. |
| **UserIdDeleted** | **string** | Optional | The unique id of the user who deleted the portfolio. |
| **RequestIdDeleted** | **string** | Optional | The unique request id of the command that deleted the portfolio. |
| **PrevailingPortfolio** | [PortfolioWithoutHref](PortfolioWithoutHref.md) | Optional | *No description available.* |
| **PrevailingInputTransaction** | [Transaction](Transaction.md) | Optional | *No description available.* |
| **DeletedPortfolio** | [PortfolioWithoutHref](PortfolioWithoutHref.md) | Optional | *No description available.* |
| **DeletedInputTransaction** | [Transaction](Transaction.md) | Optional | *No description available.* |
| **PreviewedStatus** | **string** | Optional | The status of the transaction after the staged modification is applied. Always &#39;Prevailing&#39; for transaction previews. Available values: Prevailing, Deleted, DoesNotExist. |
| **PreviewedPortfolio** | [PortfolioWithoutHref](PortfolioWithoutHref.md) | Optional | *No description available.* |
| **PreviewedInputTransaction** | [Transaction](Transaction.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionEntity(
    href: "...",  // required — The link to the transaction entity.
    entityUniqueId: "...",  // required — The unique id of the transaction, combining the portfolio and transaction identifiers.
    asAtVersionNumber: 0,  // optional — The version number of the transaction entity at the requested asAt.
    status: "...",  // required — The status of the transaction entity. &#39;Prevailing&#39; when the transaction exists — including a cancelled transaction, whose cancellation is reflected in its own status rather than here; &#39;Deleted&#39; when the transaction&#39;s portfolio has been deleted; &#39;DoesNotExist&#39; when the transaction does not yet exist (e.g. staged creation preview). Available values: Prevailing, Deleted, DoesNotExist.
    asAtDeleted: DateTimeOffset.Now,  // optional — The asAt datetime at which the portfolio (and by extension, the transaction) was deleted.
    userIdDeleted: "...",  // optional — The unique id of the user who deleted the portfolio.
    requestIdDeleted: "...",  // optional — The unique request id of the command that deleted the portfolio.
    prevailingPortfolio: new PortfolioWithoutHref(...),  // optional
    prevailingInputTransaction: new Transaction(...),  // optional
    deletedPortfolio: new PortfolioWithoutHref(...),  // optional
    deletedInputTransaction: new Transaction(...),  // optional
    previewedStatus: "...",  // optional — The status of the transaction after the staged modification is applied. Always &#39;Prevailing&#39; for transaction previews. Available values: Prevailing, Deleted, DoesNotExist.
    previewedPortfolio: new PortfolioWithoutHref(...),  // optional
    previewedInputTransaction: new Transaction(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionEntity>(json);
```

- [PortfolioWithoutHref](PortfolioWithoutHref.md)
- [Transaction](Transaction.md)
- [PortfolioWithoutHref](PortfolioWithoutHref.md)
- [Transaction](Transaction.md)
- [PortfolioWithoutHref](PortfolioWithoutHref.md)
- [Transaction](Transaction.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

