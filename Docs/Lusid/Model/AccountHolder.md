# Finbourne.Sdk.Lusid.Model.AccountHolder

An Account Holder of an Investment Account.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Optional | A client-defined key used to identify the Account Holder, unique within the Investment Account |
| **Scope** | **string** | Optional | The scope in which the Investor Record lies. |
| **Identifiers** | **Dictionary&lt;string, string&gt;** | Optional | Single Account Holder identifier that should target the desired Investor Record. |
| **EntityUniqueId** | **string** | Optional | The unique InvestorRecord entity identifier |
| **InvestorRecord** | [InvestorRecord](InvestorRecord.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AccountHolder(
    key: "...",  // optional — A client-defined key used to identify the Account Holder, unique within the Investment Account
    scope: "...",  // optional — The scope in which the Investor Record lies.
    identifiers: ,  // optional — Single Account Holder identifier that should target the desired Investor Record.
    entityUniqueId: "...",  // optional — The unique InvestorRecord entity identifier
    investorRecord: new InvestorRecord(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AccountHolder>(json);
```

- [InvestorRecord](InvestorRecord.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

