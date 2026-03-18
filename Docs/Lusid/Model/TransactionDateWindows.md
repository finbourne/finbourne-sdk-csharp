# Finbourne.Sdk.Lusid.Model.TransactionDateWindows

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | **string** | Required | Transaction Date Window for the left side of a reconciliation |
| **Right** | **string** | Required | Transaction Date Window for the right side of a reconciliation |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionDateWindows(
    left: "...",  // required — Transaction Date Window for the left side of a reconciliation
    right: "..."  // required — Transaction Date Window for the right side of a reconciliation
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionDateWindows>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

