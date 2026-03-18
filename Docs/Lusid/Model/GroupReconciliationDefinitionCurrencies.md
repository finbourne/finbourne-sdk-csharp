# Finbourne.Sdk.Lusid.Model.GroupReconciliationDefinitionCurrencies

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | **string** | Required | Currency for the left side of a reconciliation |
| **Right** | **string** | Required | Currency for the right side of a reconciliation |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationDefinitionCurrencies(
    left: "...",  // required — Currency for the left side of a reconciliation
    right: "..."  // required — Currency for the right side of a reconciliation
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationDefinitionCurrencies>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

