# Finbourne.Sdk.Lusid.Model.ShareClassData

The data for a Share Class. Includes Valuation Point Data and instrument information.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ShareClassBreakdown** | [ShareClassBreakdown](ShareClassBreakdown.md) | Required | *No description available.* |
| **ShareClassDetails** | [ShareClassDetails](ShareClassDetails.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ShareClassData(
    shareClassBreakdown: new ShareClassBreakdown(...),  // required
    shareClassDetails: new ShareClassDetails(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ShareClassData>(json);
```


## Related Models

- [ShareClassBreakdown](ShareClassBreakdown.md)
- [ShareClassDetails](ShareClassDetails.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

