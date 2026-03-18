# Finbourne.Sdk.Lusid.Model.TransactionTemplateRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Description** | **string** | Required | The description of the transaction template. |
| **ComponentTransactions** | [List&lt;ComponentTransaction&gt;](ComponentTransaction.md) | Required | A set of component transactions that relate to the template to be created. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionTemplateRequest(
    description: "...",  // required — The description of the transaction template.
    componentTransactions: new List<ComponentTransaction>()  // required — A set of component transactions that relate to the template to be created.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionTemplateRequest>(json);
```

- [ComponentTransaction](ComponentTransaction.md) — used in `ComponentTransactions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

