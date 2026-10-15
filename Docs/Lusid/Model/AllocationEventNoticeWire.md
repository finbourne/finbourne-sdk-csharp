# Finbourne.Sdk.Lusid.Model.AllocationEventNoticeWire

Wire instructions for the payment a notice asks for or announces, from the investor record's payment  instructions. Absent when the investor record holds none.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BankName** | **string** | Optional | The name of the bank. |
| **AccountName** | **string** | Optional | The name on the account. |
| **AccountNumber** | **string** | Optional | The account number or IBAN. |
| **Bic** | **string** | Optional | The bank identifier code. |
| **Reference** | **string** | Optional | The payment reference. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventNoticeWire(
    bankName: "...",  // optional — The name of the bank.
    accountName: "...",  // optional — The name on the account.
    accountNumber: "...",  // optional — The account number or IBAN.
    bic: "...",  // optional — The bank identifier code.
    reference: "..."  // optional — The payment reference.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventNoticeWire>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

