# Finbourne.Sdk.Luminesce.Model.AvailableParameter

Information about a field that can be designed on (regardless if it currently is) Kind of a \"mini-available catalog entry\"
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ProviderName** | **string** | Required | Name of the Provider with a TableParameter |
| **ParameterName** | **string** | Required | Name of the TableParameter on the Provider |
| **Fields** | [List&lt;MappableField&gt;](MappableField.md) | Required | Fields that can be mapped to |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new AvailableParameter(
    providerName: "...",  // required — Name of the Provider with a TableParameter
    parameterName: "...",  // required — Name of the TableParameter on the Provider
    fields: new List<MappableField>()  // required — Fields that can be mapped to
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AvailableParameter>(json);
```

- [MappableField](MappableField.md) — used in `Fields`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

