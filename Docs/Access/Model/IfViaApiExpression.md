# Finbourne.Sdk.Access.Model.IfViaApiExpression

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ApiFeatureCodes** | **List&lt;string&gt;** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new IfViaApiExpression(
    apiFeatureCodes:   // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IfViaApiExpression>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

