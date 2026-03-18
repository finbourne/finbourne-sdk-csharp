# Finbourne.Sdk.Workflow.Model.ValueConstraints

Constraints that should be applied to a Tasks fields
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ConstraintType** | **string** | Required | Whether the constraint is a suggestion or should be enforced via validation (e.g. Suggested, Validated) |
| **ValueSourceType** | **string** | Required | The source of the acceptable values (e.g. AcceptableValues) |
| **AcceptableValues** | **List&lt;Object&gt;** | Required | The acceptable values for the field |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ValueConstraints(
    constraintType: "...",  // required — Whether the constraint is a suggestion or should be enforced via validation (e.g. Suggested, Validated)
    valueSourceType: "...",  // required — The source of the acceptable values (e.g. AcceptableValues)
    acceptableValues:   // required — The acceptable values for the field
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ValueConstraints>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

