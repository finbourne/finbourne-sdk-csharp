# Finbourne.Sdk.Lusid.Model.BasketIdentifier

Descriptive information that describes a particular basket of instruments. Most commonly required with a CDS Index or similarly defined instrument.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Index** | **string** | Required | Index set, e.g. iTraxx or CDX. |
| **Name** | **string** | Required | The index name within the set, e.g. \&quot;MAIN\&quot; or \&quot;Crossover\&quot;. |
| **Region** | **string** | Required | Applicable geographic country or region. Typically something like \&quot;Europe\&quot;, \&quot;Asia ex-Japan\&quot;, \&quot;Japan\&quot; or \&quot;Australia\&quot;. |
| **SeriesId** | **int** | Required | The series identifier. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BasketIdentifier(
    index: "...",  // required — Index set, e.g. iTraxx or CDX.
    name: "...",  // required — The index name within the set, e.g. \&quot;MAIN\&quot; or \&quot;Crossover\&quot;.
    region: "...",  // required — Applicable geographic country or region. Typically something like \&quot;Europe\&quot;, \&quot;Asia ex-Japan\&quot;, \&quot;Japan\&quot; or \&quot;Australia\&quot;.
    seriesId: 0  // required — The series identifier.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BasketIdentifier>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

