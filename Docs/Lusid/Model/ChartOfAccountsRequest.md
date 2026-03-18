# Finbourne.Sdk.Lusid.Model.ChartOfAccountsRequest

The request used to create a chart of account.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code given for the Chart of Accounts. |
| **DisplayName** | **string** | Optional | The name of the Chart of Account. |
| **Description** | **string** | Optional | A description of the Chart of Accounts. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the Chart of Accounts. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ChartOfAccountsRequest(
    code: "...",  // required — The code given for the Chart of Accounts.
    displayName: "...",  // optional — The name of the Chart of Account.
    description: "...",  // optional — A description of the Chart of Accounts.
    properties: new Property(...)  // optional — A set of properties for the Chart of Accounts.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ChartOfAccountsRequest>(json);
```

- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

