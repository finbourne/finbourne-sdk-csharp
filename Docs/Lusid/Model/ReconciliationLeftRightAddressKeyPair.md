# Finbourne.Sdk.Lusid.Model.ReconciliationLeftRightAddressKeyPair

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | **string** | Required | Address key defined by the lhs aggregation |
| **Right** | **string** | Required | Address key defined by the rhs aggregation |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReconciliationLeftRightAddressKeyPair(
    left: "...",  // required — Address key defined by the lhs aggregation
    right: "..."  // required — Address key defined by the rhs aggregation
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReconciliationLeftRightAddressKeyPair>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

