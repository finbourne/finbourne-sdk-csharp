# Finbourne.Sdk.Lusid.Model.BucketCurrencySubtotal

A bucket's balances for one payment currency, summed across portfolios and sub-holding keys.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BucketStart** | **DateTimeOffset** | Optional | The start of the period the subtotal covers. |
| **BucketEnd** | **DateTimeOffset** | Optional | The end of the period the subtotal covers. |
| **Currency** | **string** | Optional | The payment currency. |
| **Open** | [BucketAmounts](BucketAmounts.md) | Optional | *No description available.* |
| **ActivityTotal** | [BucketAmounts](BucketAmounts.md) | Optional | *No description available.* |
| **Close** | [BucketAmounts](BucketAmounts.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketCurrencySubtotal(
    bucketStart: DateTimeOffset.Now,  // optional — The start of the period the subtotal covers.
    bucketEnd: DateTimeOffset.Now,  // optional — The end of the period the subtotal covers.
    currency: "...",  // optional — The payment currency.
    open: new BucketAmounts(...),  // optional
    activityTotal: new BucketAmounts(...),  // optional
    close: new BucketAmounts(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketCurrencySubtotal>(json);
```

- [BucketAmounts](BucketAmounts.md)
- [BucketAmounts](BucketAmounts.md)
- [BucketAmounts](BucketAmounts.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

