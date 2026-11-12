# Finbourne.Sdk.Lusid.Model.TaxClassificationException

Why an instrument could not be classified, or a flip of the qualifying-investments test a reviewer must see.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Kind** | **string** | Required | MissingInputs, ConflictingSetup, ConflictingOverride or QualifyingInvestmentsCrossing. Available values: MissingInputs, ConflictingSetup, ConflictingOverride, QualifyingInvestmentsCrossing. |
| **Code** | **string** | Required | The stable code of the exception, for filtering and routing. |
| **Message** | **string** | Required | A description of why the instrument could not be classified or why the crossing was raised. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxClassificationException(
    kind: "...",  // required — MissingInputs, ConflictingSetup, ConflictingOverride or QualifyingInvestmentsCrossing. Available values: MissingInputs, ConflictingSetup, ConflictingOverride, QualifyingInvestmentsCrossing.
    code: "...",  // required — The stable code of the exception, for filtering and routing.
    message: "..."  // required — A description of why the instrument could not be classified or why the crossing was raised.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxClassificationException>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

