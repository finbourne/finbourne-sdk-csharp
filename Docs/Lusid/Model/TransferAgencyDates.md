# Finbourne.Sdk.Lusid.Model.TransferAgencyDates

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PriceDate** | **DateTimeOffset** | Optional | The date at which the fund is priced, for the order received on ReceivedDate. Can be passed into the request instead of the ReceivedDate to calculate the TransactionDate and ExpectedPaymentDate. If both the received date and price date are given, a failure is returned. |
| **TransactionDate** | **DateTimeOffset** | Optional | The date at which the transaction into or out of the fund is made. |
| **ExpectedPaymentDate** | **DateTimeOffset** | Optional | The date by which the cash is expected to be paid to or from the fund. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransferAgencyDates(
    priceDate: DateTimeOffset.Now,  // optional — The date at which the fund is priced, for the order received on ReceivedDate. Can be passed into the request instead of the ReceivedDate to calculate the TransactionDate and ExpectedPaymentDate. If both the received date and price date are given, a failure is returned.
    transactionDate: DateTimeOffset.Now,  // optional — The date at which the transaction into or out of the fund is made.
    expectedPaymentDate: DateTimeOffset.Now,  // optional — The date by which the cash is expected to be paid to or from the fund.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransferAgencyDates>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

