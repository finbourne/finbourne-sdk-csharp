# Finbourne.Sdk.Lusid.Model.FundConfigurationRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | *No description available.* |
| **DisplayName** | **string** | Optional | The name of the Fund. |
| **Description** | **string** | Optional | A description for the Fund. |
| **DealingFilters** | [List&lt;ComponentFilter&gt;](ComponentFilter.md) | Optional | The set of filters used to decide which JE lines are included in the dealing. |
| **PnlFilters** | [List&lt;ComponentFilter&gt;](ComponentFilter.md) | Optional | The set of filters used to decide which JE lines are included in the PnL. |
| **BackOutFilters** | [List&lt;ComponentFilter&gt;](ComponentFilter.md) | Optional | The set of filters used to decide which JE lines are included in the back outs. |
| **ExternalFeeFilters** | [List&lt;ExternalFeeComponentFilter&gt;](ExternalFeeComponentFilter.md) | Optional | The set of filters used to decide which JE lines are used for inputting fees from an external source. |
| **BucketSets** | [List&lt;BucketSetDefinition&gt;](BucketSetDefinition.md) | Optional | The ordered set of component bucket set definitions for this fund configuration. Each bucket set defines how JE lines are grouped into buckets at VP finalisation. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the Fund Configuration. |
| **ApportionmentBucketSet** | **string** | Optional | The code of the bucket set definition within this fund configuration that is designated as the apportionment bucket set. Must reference a BucketSetDefinition code within the BucketSets collection. |
| **ApportionmentMethodProperty** | [ApportionmentMethodProperty](ApportionmentMethodProperty.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundConfigurationRequest(
    code: "...",  // required
    displayName: "...",  // optional — The name of the Fund.
    description: "...",  // optional — A description for the Fund.
    dealingFilters: new List<ComponentFilter>(),  // optional — The set of filters used to decide which JE lines are included in the dealing.
    pnlFilters: new List<ComponentFilter>(),  // optional — The set of filters used to decide which JE lines are included in the PnL.
    backOutFilters: new List<ComponentFilter>(),  // optional — The set of filters used to decide which JE lines are included in the back outs.
    externalFeeFilters: new List<ExternalFeeComponentFilter>(),  // optional — The set of filters used to decide which JE lines are used for inputting fees from an external source.
    bucketSets: new List<BucketSetDefinition>(),  // optional — The ordered set of component bucket set definitions for this fund configuration. Each bucket set defines how JE lines are grouped into buckets at VP finalisation.
    properties: new Property(...),  // optional — A set of properties for the Fund Configuration.
    apportionmentBucketSet: "...",  // optional — The code of the bucket set definition within this fund configuration that is designated as the apportionment bucket set. Must reference a BucketSetDefinition code within the BucketSets collection.
    apportionmentMethodProperty: new ApportionmentMethodProperty(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundConfigurationRequest>(json);
```

- [ComponentFilter](ComponentFilter.md) — used in `DealingFilters`
- [ComponentFilter](ComponentFilter.md) — used in `PnlFilters`
- [ComponentFilter](ComponentFilter.md) — used in `BackOutFilters`
- [ExternalFeeComponentFilter](ExternalFeeComponentFilter.md) — used in `ExternalFeeFilters`
- [BucketSetDefinition](BucketSetDefinition.md) — used in `BucketSets`
- [Property](Property.md) — used in `Properties`
- [ApportionmentMethodProperty](ApportionmentMethodProperty.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

