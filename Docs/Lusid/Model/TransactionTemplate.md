# Finbourne.Sdk.Lusid.Model.TransactionTemplate

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentType** | **string** | Required | A value that represents the instrument type. |
| **InstrumentEventType** | **string** | Required | A value that represents the instrument event type. |
| **Description** | **string** | Required | The description of the transaction template. |
| **Scope** | **string** | Required | The scope in which the transaction template resides. |
| **ComponentTransactions** | [List&lt;ComponentTransaction&gt;](ComponentTransaction.md) | Required | A set of component transactions that relate to the template to be created. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionTemplate(
    instrumentType: "...",  // required — A value that represents the instrument type.
    instrumentEventType: "...",  // required — A value that represents the instrument event type.
    description: "...",  // required — The description of the transaction template.
    scope: "...",  // required — The scope in which the transaction template resides.
    componentTransactions: new List<ComponentTransaction>(),  // required — A set of component transactions that relate to the template to be created.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionTemplate>(json);
```

- [ComponentTransaction](ComponentTransaction.md) — used in `ComponentTransactions`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

