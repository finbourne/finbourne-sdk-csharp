# Finbourne.Sdk.Lusid.Model.AdditionalPayment

Record describing additional payment entity.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Amount** | **decimal** | Required | The payment amount. |
| **Currency** | **string** | Required | The payment currency. |
| **PayDate** | **DateTimeOffset** | Required | Date when the payment is made. |
| **PayReceive** | **string** | Required | Is it pay or receive.    Supported string (enumeration) values are: [Pay, Receive]. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AdditionalPayment(
    amount: 0.0d,  // required — The payment amount.
    currency: "...",  // required — The payment currency.
    payDate: DateTimeOffset.Now,  // required — Date when the payment is made.
    payReceive: "..."  // required — Is it pay or receive.    Supported string (enumeration) values are: [Pay, Receive].
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AdditionalPayment>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

