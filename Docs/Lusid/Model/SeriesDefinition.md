# Finbourne.Sdk.Lusid.Model.SeriesDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SeriesIdentifier** | **string** | Required | The identifier that uniquely identifies this Series within the Share Class. |
| **SeriesType** | **string** | Required | The type of the Series. Valid values are: Lead, Standard. |
| **LaunchDate** | **DateTimeOffset** | Required | The date on which the Series was launched. |
| **LaunchPriceType** | **string** | Required | The type of launch price for the Series. Valid values are: Manual, Calculated. |
| **DomCcy** | **string** | Required | The denomination currency of the Series. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | An optional set of properties to associate with the Series. Only applied if createInstrument is set to true on the parent Fund. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SeriesDefinition(
    seriesIdentifier: "...",  // required — The identifier that uniquely identifies this Series within the Share Class.
    seriesType: "...",  // required — The type of the Series. Valid values are: Lead, Standard.
    launchDate: DateTimeOffset.Now,  // required — The date on which the Series was launched.
    launchPriceType: "...",  // required — The type of launch price for the Series. Valid values are: Manual, Calculated.
    domCcy: "...",  // required — The denomination currency of the Series.
    properties: new Property(...)  // optional — An optional set of properties to associate with the Series. Only applied if createInstrument is set to true on the parent Fund.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SeriesDefinition>(json);
```

- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

