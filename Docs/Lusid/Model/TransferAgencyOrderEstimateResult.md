# Finbourne.Sdk.Lusid.Model.TransferAgencyOrderEstimateResult

The estimated values for one order, together with the market facts they were struck from. The market facts  are repeated on every order priced against the same share class so that each result stands alone.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OrderId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **MostRecentValuationDate** | **DateTimeOffset** | Optional | *No description available.* |
| **PricePerShare** | **decimal** | Optional | *No description available.* |
| **PriceCurrency** | **string** | Optional | *No description available.* |
| **EstimatedUnits** | **decimal** | Optional | *No description available.* |
| **EstimatedAmount** | **decimal** | Optional | *No description available.* |
| **EstimatedAmountCurrency** | **string** | Optional | *No description available.* |
| **FxRateUsed** | **decimal** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransferAgencyOrderEstimateResult(
    orderId: new ResourceId(...),  // optional
    mostRecentValuationDate: DateTimeOffset.Now,  // optional
    pricePerShare: 0.0d,  // optional
    priceCurrency: "...",  // optional
    estimatedUnits: 0.0d,  // optional
    estimatedAmount: 0.0d,  // optional
    estimatedAmountCurrency: "...",  // optional
    fxRateUsed: 0.0d  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransferAgencyOrderEstimateResult>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

