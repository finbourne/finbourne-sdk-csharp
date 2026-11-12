# Finbourne.Sdk.Lusid.Model.RevaluationProblem

A reason why a revaluation amount could not be populated.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Optional | A machine-readable code identifying the type of problem (e.g. MissingFxRate, MissingBookedFxRate). |
| **Message** | **string** | Optional | A human-readable description of why the revaluation amount could not be populated. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RevaluationProblem(
    code: "...",  // optional — A machine-readable code identifying the type of problem (e.g. MissingFxRate, MissingBookedFxRate).
    message: "..."  // optional — A human-readable description of why the revaluation amount could not be populated.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RevaluationProblem>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

