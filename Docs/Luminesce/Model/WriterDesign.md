# Finbourne.Sdk.Luminesce.Model.WriterDesign

Representation of a \"designable Query for a writer\" suitable for formatting to SQL or being built from compliant SQL.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Sql** | **string** | Required | Original SQL that started this off |
| **AvailableToMapFrom** | [List&lt;ExpressionWithAlias&gt;](ExpressionWithAlias.md) | Optional | The data able to be mapped from as derived from the Sql |
| **Parameter** | [AvailableParameter](AvailableParameter.md) | Optional | *No description available.* |
| **AvailableParameters** | [List&lt;AvailableParameter&gt;](AvailableParameter.md) | Optional | All the parameter the user may wish to design |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new WriterDesign(
    sql: "...",  // required — Original SQL that started this off
    availableToMapFrom: new List<ExpressionWithAlias>(),  // optional — The data able to be mapped from as derived from the Sql
    varParameter: new AvailableParameter(...),  // optional
    availableParameters: new List<AvailableParameter>()  // optional — All the parameter the user may wish to design
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WriterDesign>(json);
```

- [ExpressionWithAlias](ExpressionWithAlias.md) — used in `AvailableToMapFrom`
- [AvailableParameter](AvailableParameter.md)
- [AvailableParameter](AvailableParameter.md) — used in `AvailableParameters`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

