# Finbourne.Sdk.Lusid.Model.ComparisonAttributeValuePair

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AttributeName** | **string** | Required | Comparison rule attribute name. |
| **Value** | **string** | Optional | Computed value for the comparison rule attribute. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComparisonAttributeValuePair(
    attributeName: "...",  // required — Comparison rule attribute name.
    value: "..."  // optional — Computed value for the comparison rule attribute.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComparisonAttributeValuePair>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

