# Finbourne.Sdk.Lusid.Model.RecDefSideNames

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | **string** | Required | The label for the left side of the reconciliation. |
| **Right** | **string** | Required | The label for the right side of the reconciliation. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecDefSideNames(
    left: "...",  // required — The label for the left side of the reconciliation.
    right: "..."  // required — The label for the right side of the reconciliation.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecDefSideNames>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

