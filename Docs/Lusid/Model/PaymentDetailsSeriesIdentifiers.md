# Finbourne.Sdk.Lusid.Model.PaymentDetailsSeriesIdentifiers

The two hardcoded series identifier keys that uniquely identify a Payment Details data series.  The currency value must match the top-level currency field on the Payment Instruction.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PaymentType** | **string** | Required | The type of payment series. One of \&quot;Dividend\&quot;, \&quot;Fee\&quot;, \&quot;Rebate\&quot;, \&quot;Redemption\&quot;, \&quot;Subscription\&quot;. |
| **Currency** | **string** | Required | ISO 4217 currency code identifying the currency-specific series row. Must match the top-level currency field. |
| **CustodianAccountScope** | **string** | Optional | Optional. The scope of the custodian account on the portfolio. Only permitted when the applicable entity is a Portfolio. |
| **CustodianAccountCode** | **string** | Optional | Optional. The code of the custodian account on the portfolio. Only permitted when the applicable entity is a Portfolio. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PaymentDetailsSeriesIdentifiers(
    paymentType: "...",  // required — The type of payment series. One of \&quot;Dividend\&quot;, \&quot;Fee\&quot;, \&quot;Rebate\&quot;, \&quot;Redemption\&quot;, \&quot;Subscription\&quot;.
    currency: "...",  // required — ISO 4217 currency code identifying the currency-specific series row. Must match the top-level currency field.
    custodianAccountScope: "...",  // optional — Optional. The scope of the custodian account on the portfolio. Only permitted when the applicable entity is a Portfolio.
    custodianAccountCode: "..."  // optional — Optional. The code of the custodian account on the portfolio. Only permitted when the applicable entity is a Portfolio.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PaymentDetailsSeriesIdentifiers>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

