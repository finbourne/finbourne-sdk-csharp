# Finbourne.Sdk.Lusid.Model.PartnerStatementLine

One figure on a partner statement.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | The key of the figure. |
| **Label** | **string** | Required | The label of the figure. |
| **Amount** | **decimal** | Required | The amount of the figure. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerStatementLine(
    key: "...",  // required — The key of the figure.
    label: "...",  // required — The label of the figure.
    amount: 0.0d  // required — The amount of the figure.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnerStatementLine>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

