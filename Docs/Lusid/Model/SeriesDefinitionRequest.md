# Finbourne.Sdk.Lusid.Model.SeriesDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ShareClassCode** | **string** | Required | The code of the Share Class this Series belongs to. |
| **SeriesDefinitions** | [List&lt;SeriesDefinition&gt;](SeriesDefinition.md) | Required | The definitions of the Series to add to the Share Class. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SeriesDefinitionRequest(
    shareClassCode: "...",  // required — The code of the Share Class this Series belongs to.
    seriesDefinitions: new List<SeriesDefinition>()  // required — The definitions of the Series to add to the Share Class.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SeriesDefinitionRequest>(json);
```

- [SeriesDefinition](SeriesDefinition.md) — used in `SeriesDefinitions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

