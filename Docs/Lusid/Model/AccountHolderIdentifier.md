# Finbourne.Sdk.Lusid.Model.AccountHolderIdentifier

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | A client-defined key used to identify the Account Holder, unique within the Investment Account |
| **Scope** | **string** | Required | The scope in which the Investor Record lies. |
| **Identifiers** | **Dictionary&lt;string, string&gt;** | Required | Single Account Holder identifier that should target the desired Investor Record. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AccountHolderIdentifier(
    key: "...",  // required — A client-defined key used to identify the Account Holder, unique within the Investment Account
    scope: "...",  // required — The scope in which the Investor Record lies.
    identifiers:   // required — Single Account Holder identifier that should target the desired Investor Record.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AccountHolderIdentifier>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

