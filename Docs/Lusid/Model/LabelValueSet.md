# Finbourne.Sdk.Lusid.Model.LabelValueSet

The set of string labels in a multi-value property.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | **List&lt;string&gt;** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new LabelValueSet(
    values:   // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LabelValueSet>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

