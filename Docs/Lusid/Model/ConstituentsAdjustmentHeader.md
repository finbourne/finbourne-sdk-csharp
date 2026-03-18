# Finbourne.Sdk.Lusid.Model.ConstituentsAdjustmentHeader

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveAt** | **DateTimeOffset** | Optional | There can be at most one holdings adjustment for a portfolio at a  specific effective time so this uniquely identifies the adjustment. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ConstituentsAdjustmentHeader(
    effectiveAt: DateTimeOffset.Now,  // optional — There can be at most one holdings adjustment for a portfolio at a  specific effective time so this uniquely identifies the adjustment.
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
var instance = JsonConvert.DeserializeObject<ConstituentsAdjustmentHeader>(json);
```

- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

