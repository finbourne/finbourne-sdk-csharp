# Finbourne.Sdk.Lusid.Model.Transfer

A transfer and both of the transactions it booked.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransferId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **TransferType** | **string** | Optional | The derived type of the transfer: &#39;Transfer&#39; when the position moves between portfolios, &#39;Switch&#39; when one instrument is exchanged for another within a portfolio, and &#39;Twitch&#39; when the position moves between portfolios and changes instrument at the same time. |
| **PortfolioIdOut** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **PortfolioIdIn** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **PricingMethod** | **string** | Optional | How the legs were priced: &#39;AtCost&#39; or &#39;AtPrice&#39;. |
| **TaxLotStructure** | **string** | Optional | What happened to the tax lots of the outgoing position: &#39;Consolidate&#39; or &#39;Preserve&#39;. |
| **WeightOut** | **decimal?** | Optional | The weighting factor recorded against the outgoing leg. |
| **AccountingMethod** | **string** | Optional | The accounting method recorded against the transfer. |
| **TransactionOut** | [Transaction](Transaction.md) | Optional | *No description available.* |
| **TransactionIn** | [Transaction](Transaction.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The properties of the transfer, for the requested PropertyKeys. |
| **Href** | **string** | Optional | The specifc Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Transfer(
    transferId: new ResourceId(...),  // optional
    transferType: "...",  // optional — The derived type of the transfer: &#39;Transfer&#39; when the position moves between portfolios, &#39;Switch&#39; when one instrument is exchanged for another within a portfolio, and &#39;Twitch&#39; when the position moves between portfolios and changes instrument at the same time.
    portfolioIdOut: new ResourceId(...),  // optional
    portfolioIdIn: new ResourceId(...),  // optional
    pricingMethod: "...",  // optional — How the legs were priced: &#39;AtCost&#39; or &#39;AtPrice&#39;.
    taxLotStructure: "...",  // optional — What happened to the tax lots of the outgoing position: &#39;Consolidate&#39; or &#39;Preserve&#39;.
    weightOut: 0.0d,  // optional — The weighting factor recorded against the outgoing leg.
    accountingMethod: "...",  // optional — The accounting method recorded against the transfer.
    transactionOut: new Transaction(...),  // optional
    transactionIn: new Transaction(...),  // optional
    properties: new Property(...),  // optional — The properties of the transfer, for the requested PropertyKeys.
    href: "...",  // optional — The specifc Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
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
var instance = JsonConvert.DeserializeObject<Transfer>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [Transaction](Transaction.md)
- [Transaction](Transaction.md)
- [Property](Property.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

