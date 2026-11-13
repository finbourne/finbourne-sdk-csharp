# Finbourne.Sdk.Lusid.Model.TaxReturnTransitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Reason** | **string** | Required | The reason for advancing or sending back the return. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxReturnTransitionRequest(
    reason: "..."  // required — The reason for advancing or sending back the return.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxReturnTransitionRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

