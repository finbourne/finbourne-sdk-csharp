# Finbourne.Sdk.Lusid.Model.PropertyReferenceDataValue

The ReferenceData relevant to the property. The ReferenceData is taken from the DataType on the PropertyDefinition that defines the Property.  Only ReferenceData where the ReferenceData value matches the Property value is included.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StringValue** | **string** | Optional | *No description available.* |
| **NumericValue** | **decimal?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PropertyReferenceDataValue(
    stringValue: "...",  // optional
    numericValue: 0.0d  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PropertyReferenceDataValue>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

