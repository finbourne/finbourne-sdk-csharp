# Finbourne.Sdk.Lusid.Model.ElectionSpecification

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ElectionType** | **string** | Required | *No description available.* |
| **Cardinality** | **Dictionary&lt;string, string&gt;** | Required | *No description available.* |
| **ReferencedAs** | **List&lt;string&gt;** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ElectionSpecification(
    electionType: "...",  // required
    cardinality: ,  // required
    referencedAs:   // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ElectionSpecification>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

