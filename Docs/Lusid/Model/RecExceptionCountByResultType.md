# Finbourne.Sdk.Lusid.Model.RecExceptionCountByResultType

Exception result counts broken down by result type.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Break** | **int** | Required | The number of Break results. |
| **PartialMatch** | **int** | Required | The number of Partial Match results. |
| **PartialCross** | **int** | Required | The number of Partial Cross results. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecExceptionCountByResultType(
    varBreak: 0,  // required — The number of Break results.
    partialMatch: 0,  // required — The number of Partial Match results.
    partialCross: 0  // required — The number of Partial Cross results.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecExceptionCountByResultType>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

