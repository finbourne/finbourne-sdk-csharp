# Finbourne.Sdk.Lusid.Model.MarketDataFieldConfiguration

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MarketDataCategory** | **string** | Required | The category of market data this configuration applies to. Available values: Quote, Complex. |
| **Scope** | **string** | Required | The scope of the market data field configuration. |
| **MetadataFieldSchema** | [List&lt;MetadataFieldDefinition&gt;](MetadataFieldDefinition.md) | Required | The metadata field definitions for this configuration. |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarketDataFieldConfiguration(
    marketDataCategory: "...",  // required — The category of market data this configuration applies to. Available values: Quote, Complex.
    scope: "...",  // required — The scope of the market data field configuration.
    metadataFieldSchema: new List<MetadataFieldDefinition>(),  // required — The metadata field definitions for this configuration.
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
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
var instance = JsonConvert.DeserializeObject<MarketDataFieldConfiguration>(json);
```

- [MetadataFieldDefinition](MetadataFieldDefinition.md) — used in `MetadataFieldSchema`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

