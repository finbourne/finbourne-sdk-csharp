# Finbourne.Sdk.Lusid.Model.PackAccount

An account on a partnership configuration pack's chart of accounts.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The account code. |
| **Name** | **string** | Required | The account name. |
| **Type** | **string** | Required | The account type: Asset, Liability, Capital, Income or Expense. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PackAccount(
    code: "...",  // required — The account code.
    name: "...",  // required — The account name.
    type: "..."  // required — The account type: Asset, Liability, Capital, Income or Expense.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PackAccount>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

