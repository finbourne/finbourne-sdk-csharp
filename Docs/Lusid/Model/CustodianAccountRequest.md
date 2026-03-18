# Finbourne.Sdk.Lusid.Model.CustodianAccountRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Optional | The Scope assigned to the Custodian Account, where left blank the parent Portfolio Scope will be used |
| **Code** | **string** | Required | Unique Code representing the Custodian Account |
| **Status** | **string** | Optional | The Account status. Can be Active, Inactive or Deleted. |
| **AccountNumber** | **string** | Required | The Custodian Account Number |
| **AccountName** | **string** | Required | The identifiable name given to the Custodian Account |
| **AccountingMethod** | **string** | Required | The Accounting method to be used |
| **Currency** | **string** | Required | The Currency for the Account |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | Set of unique Custodian Account properties and associated values to store with the Custodian Account. Each property must be from the &#39;CustodianAccount&#39; domain. |
| **CustodianIdentifier** | [TypedResourceId](TypedResourceId.md) | Required | *No description available.* |
| **AccountType** | **string** | Optional | The Type of the Custodian Account. Can be Margin, Cash or Swap. Defaults to Margin. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CustodianAccountRequest(
    scope: "...",  // optional — The Scope assigned to the Custodian Account, where left blank the parent Portfolio Scope will be used
    code: "...",  // required — Unique Code representing the Custodian Account
    status: "...",  // optional — The Account status. Can be Active, Inactive or Deleted.
    accountNumber: "...",  // required — The Custodian Account Number
    accountName: "...",  // required — The identifiable name given to the Custodian Account
    accountingMethod: "...",  // required — The Accounting method to be used
    currency: "...",  // required — The Currency for the Account
    properties: new Property(...),  // optional — Set of unique Custodian Account properties and associated values to store with the Custodian Account. Each property must be from the &#39;CustodianAccount&#39; domain.
    custodianIdentifier: new TypedResourceId(...),  // required
    accountType: "..."  // optional — The Type of the Custodian Account. Can be Margin, Cash or Swap. Defaults to Margin.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustodianAccountRequest>(json);
```

- [Property](Property.md) — used in `Properties`
- [TypedResourceId](TypedResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

