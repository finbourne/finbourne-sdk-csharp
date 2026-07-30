# Finbourne.Sdk.Lusid.Model.RecExceptionCountByClosureType

Closed exception result counts broken down by closure type.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Cleared** | **int** | Required | The number of Cleared results. |
| **Accepted** | **int** | Required | The number of Accepted results. |
| **ForceMatched** | **int** | Required | The number of Force Matched results. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecExceptionCountByClosureType(
    cleared: 0,  // required — The number of Cleared results.
    accepted: 0,  // required — The number of Accepted results.
    forceMatched: 0  // required — The number of Force Matched results.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecExceptionCountByClosureType>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

