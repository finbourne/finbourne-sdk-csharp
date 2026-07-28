# Finbourne.Sdk.Lusid.Model.PaymentDetailsApplicableEntity

Identifies the LUSID entity that holds the payment details (e.g. an InvestorRecord or Portfolio).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityType** | **string** | Required | The type of the LUSID entity holding the payment details. e.g. \&quot;InvestorRecord\&quot;, \&quot;InvestmentAccount\&quot;, \&quot;Portfolio\&quot;. |
| **EntityScope** | **string** | Optional | The scope of the entity. Optional — required depends on the entity type. |
| **IdentifierType** | **string** | Required | The identifier type used to identify the entity. e.g. \&quot;lusidInvestmentAccountId\&quot;. |
| **IdentifierScope** | **string** | Optional | The scope of the identifier used to identify the entity. Optional — null for native LUSID identifiers such as code. |
| **IdentifierValue** | **string** | Required | The identifier value for the entity. e.g. \&quot;LUID_00003DNL\&quot;. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PaymentDetailsApplicableEntity(
    entityType: "...",  // required — The type of the LUSID entity holding the payment details. e.g. \&quot;InvestorRecord\&quot;, \&quot;InvestmentAccount\&quot;, \&quot;Portfolio\&quot;.
    entityScope: "...",  // optional — The scope of the entity. Optional — required depends on the entity type.
    identifierType: "...",  // required — The identifier type used to identify the entity. e.g. \&quot;lusidInvestmentAccountId\&quot;.
    identifierScope: "...",  // optional — The scope of the identifier used to identify the entity. Optional — null for native LUSID identifiers such as code.
    identifierValue: "..."  // required — The identifier value for the entity. e.g. \&quot;LUID_00003DNL\&quot;.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PaymentDetailsApplicableEntity>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

