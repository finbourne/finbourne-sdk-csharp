# Finbourne.Sdk.Lusid.Model.ValuationAddressKeyTemplate

A set of valuation metrics and grouping keys. Funds and NAV Types reference a template by its id.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Optional | The name of the Valuation Template. |
| **Description** | **string** | Optional | A description of the Valuation Template. |
| **Metrics** | [List&lt;AggregateSpec&gt;](AggregateSpec.md) | Optional | The metrics to calculate in a valuation that uses this template. Each metric is an address key, an operation and optional key options. Valuation Templates do not support returnAs. |
| **IsDefault** | **bool** | Optional | True if this is the default Valuation Template, which applies when neither the Fund nor the NAV Type references a template. A domain has one default. Set isDefault on UpsertValuationAddressKeyTemplate to change it. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ValuationAddressKeyTemplate(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    id: new ResourceId(...),  // required
    displayName: "...",  // optional — The name of the Valuation Template.
    description: "...",  // optional — A description of the Valuation Template.
    metrics: new List<AggregateSpec>(),  // optional — The metrics to calculate in a valuation that uses this template. Each metric is an address key, an operation and optional key options. Valuation Templates do not support returnAs.
    isDefault: true,  // optional — True if this is the default Valuation Template, which applies when neither the Fund nor the NAV Type references a template. A domain has one default. Set isDefault on UpsertValuationAddressKeyTemplate to change it.
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
var instance = JsonConvert.DeserializeObject<ValuationAddressKeyTemplate>(json);
```

- [ResourceId](ResourceId.md)
- [AggregateSpec](AggregateSpec.md) — used in `Metrics`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

