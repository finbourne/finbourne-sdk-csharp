# Finbourne.Sdk.Lusid.Model.FundConfiguration

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Optional | The name of the FundConfiguration. |
| **Description** | **string** | Optional | A description for the FundConfiguration. |
| **DealingFilters** | [List&lt;ComponentFilter&gt;](ComponentFilter.md) | Optional | The set of filters used to decide which JE lines are included in the dealing. |
| **PnlFilters** | [List&lt;ComponentFilter&gt;](ComponentFilter.md) | Optional | The set of filters used to decide which JE lines are included in the PnL. |
| **BackOutFilters** | [List&lt;ComponentFilter&gt;](ComponentFilter.md) | Optional | The set of filters used to decide which JE lines are included in the back outs. |
| **ExternalFeeFilters** | [List&lt;ExternalFeeComponentFilter&gt;](ExternalFeeComponentFilter.md) | Optional | The set of filters used to decide which JE lines are used for inputting fees from an external source. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the Fund Configuration. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundConfiguration(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    id: new ResourceId(...),  // required
    displayName: "...",  // optional — The name of the FundConfiguration.
    description: "...",  // optional — A description for the FundConfiguration.
    dealingFilters: new List<ComponentFilter>(),  // optional — The set of filters used to decide which JE lines are included in the dealing.
    pnlFilters: new List<ComponentFilter>(),  // optional — The set of filters used to decide which JE lines are included in the PnL.
    backOutFilters: new List<ComponentFilter>(),  // optional — The set of filters used to decide which JE lines are included in the back outs.
    externalFeeFilters: new List<ExternalFeeComponentFilter>(),  // optional — The set of filters used to decide which JE lines are used for inputting fees from an external source.
    properties: new Property(...),  // optional — A set of properties for the Fund Configuration.
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
var instance = JsonConvert.DeserializeObject<FundConfiguration>(json);
```

- [ResourceId](ResourceId.md)
- [ComponentFilter](ComponentFilter.md) — used in `DealingFilters`
- [ComponentFilter](ComponentFilter.md) — used in `PnlFilters`
- [ComponentFilter](ComponentFilter.md) — used in `BackOutFilters`
- [ExternalFeeComponentFilter](ExternalFeeComponentFilter.md) — used in `ExternalFeeFilters`
- [Property](Property.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

