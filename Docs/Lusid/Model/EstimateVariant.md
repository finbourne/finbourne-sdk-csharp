# Finbourne.Sdk.Lusid.Model.EstimateVariant

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Variant** | **string** | Optional | The Variant of the Calendar Entry. Together with the valuation point code marks the unique branch for the NavType. |
| **DisplayName** | **string** | Required | The name of the Fund Calendar entry. |
| **Description** | **string** | Optional | A description for the Fund Calendar entry. |
| **AsAt** | **DateTimeOffset** | Required | The asAt datetime for the Calendar Entry. |
| **HoldingsAsAtOverride** | **DateTimeOffset?** | Optional | The optional AsAt Override to use for building holdings in the Valuation Point. Defaults to Latest. |
| **ValuationsAsAtOverride** | **DateTimeOffset?** | Optional | The optional AsAt Override to use for performing valuations in the Valuation Point. Defaults to Latest. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The properties for the Calendar Entry. These will be from the &#39;ClosedPeriod&#39; domain. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EstimateVariant(
    variant: "...",  // optional — The Variant of the Calendar Entry. Together with the valuation point code marks the unique branch for the NavType.
    displayName: "...",  // required — The name of the Fund Calendar entry.
    description: "...",  // optional — A description for the Fund Calendar entry.
    asAt: DateTimeOffset.Now,  // required — The asAt datetime for the Calendar Entry.
    holdingsAsAtOverride: DateTimeOffset.Now,  // optional — The optional AsAt Override to use for building holdings in the Valuation Point. Defaults to Latest.
    valuationsAsAtOverride: DateTimeOffset.Now,  // optional — The optional AsAt Override to use for performing valuations in the Valuation Point. Defaults to Latest.
    properties: new Property(...),  // optional — The properties for the Calendar Entry. These will be from the &#39;ClosedPeriod&#39; domain.
    varVersion: new ModelVersion(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EstimateVariant>(json);
```

- [Property](Property.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

