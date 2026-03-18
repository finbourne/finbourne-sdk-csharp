# Finbourne.Sdk.Lusid.Model.FundConfigurationRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | *No description available.* |
| **DisplayName** | **string** | Optional | The name of the Fund. |
| **Description** | **string** | Optional | A description for the Fund. |
| **DealingFilters** | [List&lt;ComponentFilter&gt;](ComponentFilter.md) | Required | The set of filters used to decide which JE lines are included in the dealing. |
| **PnlFilters** | [List&lt;ComponentFilter&gt;](ComponentFilter.md) | Required | The set of filters used to decide which JE lines are included in the PnL. |
| **BackOutFilters** | [List&lt;ComponentFilter&gt;](ComponentFilter.md) | Required | The set of filters used to decide which JE lines are included in the back outs. |
| **ExternalFeeFilters** | [List&lt;ExternalFeeComponentFilter&gt;](ExternalFeeComponentFilter.md) | Optional | The set of filters used to decide which JE lines are used for inputting fees from an external source. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the Fund Configuration. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundConfigurationRequest(
    code: "...",  // required
    displayName: "...",  // optional — The name of the Fund.
    description: "...",  // optional — A description for the Fund.
    dealingFilters: new List<ComponentFilter>(),  // required — The set of filters used to decide which JE lines are included in the dealing.
    pnlFilters: new List<ComponentFilter>(),  // required — The set of filters used to decide which JE lines are included in the PnL.
    backOutFilters: new List<ComponentFilter>(),  // required — The set of filters used to decide which JE lines are included in the back outs.
    externalFeeFilters: new List<ExternalFeeComponentFilter>(),  // optional — The set of filters used to decide which JE lines are used for inputting fees from an external source.
    properties: new Property(...)  // optional — A set of properties for the Fund Configuration.
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
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

