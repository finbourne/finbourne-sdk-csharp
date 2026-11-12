# Finbourne.Sdk.Lusid.Model.TaxExceptionRootCause

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | A stable code for the cause, for example PoolOutOfSync or MissingTreatmentLeaf. |
| **Label** | **string** | Required | A display label for the cause. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxExceptionRootCause(
    code: "...",  // required — A stable code for the cause, for example PoolOutOfSync or MissingTreatmentLeaf.
    label: "..."  // required — A display label for the cause.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxExceptionRootCause>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

