# Finbourne.Sdk.Lusid.Model.StagedModificationsRequestedChangeInterval

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AttributeName** | **string** | Optional | Name of the property the change applies to. |
| **EffectiveRange** | [StagedModificationEffectiveRange](StagedModificationEffectiveRange.md) | Optional | *No description available.* |
| **PreviousValue** | [PropertyValue](PropertyValue.md) | Optional | *No description available.* |
| **NewValue** | [PropertyValue](PropertyValue.md) | Optional | *No description available.* |
| **AsAtBasis** | **string** | Optional | Whether the change represents the modification when the request was made or the modification as it would be at the latest time. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StagedModificationsRequestedChangeInterval(
    attributeName: "...",  // optional — Name of the property the change applies to.
    effectiveRange: new StagedModificationEffectiveRange(...),  // optional
    previousValue: new PropertyValue(...),  // optional
    newValue: new PropertyValue(...),  // optional
    asAtBasis: "...",  // optional — Whether the change represents the modification when the request was made or the modification as it would be at the latest time.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StagedModificationsRequestedChangeInterval>(json);
```

- [StagedModificationEffectiveRange](StagedModificationEffectiveRange.md)
- [PropertyValue](PropertyValue.md)
- [PropertyValue](PropertyValue.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

