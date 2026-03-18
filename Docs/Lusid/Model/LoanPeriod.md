# Finbourne.Sdk.Lusid.Model.LoanPeriod

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PaymentDate** | **DateTimeOffset** | Required | *No description available.* |
| **Notional** | **decimal** | Required | *No description available.* |
| **InterestAmount** | **decimal** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new LoanPeriod(
    paymentDate: DateTimeOffset.Now,  // required
    notional: 0.0d,  // required
    interestAmount: 0.0d  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LoanPeriod>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

