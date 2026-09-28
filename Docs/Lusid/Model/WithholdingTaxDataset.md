# Finbourne.Sdk.Lusid.Model.WithholdingTaxDataset

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope of the relational dataset definition. |
| **Code** | **string** | Required | The code of the relational dataset definition. Together with the scope this uniquely identifies the definition. |
| **Dimensions** | [List&lt;SeriesIdentifierField&gt;](SeriesIdentifierField.md) | Required | The dimensions created on this dataset as series identifiers, as stored. The mandatory core is not returned here; read the full field schema from the relational dataset definition at Href. |
| **Href** | **string** | Optional | The specific Uri of the relational dataset definition. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WithholdingTaxDataset(
    scope: "...",  // required — The scope of the relational dataset definition.
    code: "...",  // required — The code of the relational dataset definition. Together with the scope this uniquely identifies the definition.
    dimensions: new List<SeriesIdentifierField>(),  // required — The dimensions created on this dataset as series identifiers, as stored. The mandatory core is not returned here; read the full field schema from the relational dataset definition at Href.
    href: "...",  // optional — The specific Uri of the relational dataset definition.
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WithholdingTaxDataset>(json);
```

- [SeriesIdentifierField](SeriesIdentifierField.md) — used in `Dimensions`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

