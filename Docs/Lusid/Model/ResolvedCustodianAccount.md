# Finbourne.Sdk.Lusid.Model.ResolvedCustodianAccount

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AccountSelector** | **string** | Optional | Available values: From, To. |
| **CustodianAccount** | [CustodianAccount](CustodianAccount.md) | Required | *No description available.* |
| **ResolutionType** | **string** | Required | Available values: BookingEntry, ContextCustodian, RelatedAccount, PortfolioDefault. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ResolvedCustodianAccount(
    accountSelector: "...",  // optional — Available values: From, To.
    custodianAccount: new CustodianAccount(...),  // required
    resolutionType: "..."  // required — Available values: BookingEntry, ContextCustodian, RelatedAccount, PortfolioDefault.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResolvedCustodianAccount>(json);
```

- [CustodianAccount](CustodianAccount.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

