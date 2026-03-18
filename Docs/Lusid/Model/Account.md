# Finbourne.Sdk.Lusid.Model.Account

An account
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code given for the Account. |
| **Description** | **string** | Optional | A description for the Account. |
| **Type** | **string** | Required | The Account type. Can have the values: Asset/Liabilities/Income/Expense/Capital/Revenue. |
| **Status** | **string** | Required | The Account status. Can be Active, Inactive or Deleted. The available values are: Active, Inactive, Deleted |
| **Control** | **string** | Optional | This allows users to specify whether this a protected Account that prevents direct manual journal adjustment. Can have the values: System/ManualIt will default to “Manual”. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the Account. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Account(
    code: "...",  // required — The code given for the Account.
    description: "...",  // optional — A description for the Account.
    type: "...",  // required — The Account type. Can have the values: Asset/Liabilities/Income/Expense/Capital/Revenue.
    status: "...",  // required — The Account status. Can be Active, Inactive or Deleted. The available values are: Active, Inactive, Deleted
    control: "...",  // optional — This allows users to specify whether this a protected Account that prevents direct manual journal adjustment. Can have the values: System/ManualIt will default to “Manual”.
    properties: new Property(...)  // optional — A set of properties for the Account.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Account>(json);
```

- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

