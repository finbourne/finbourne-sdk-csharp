# Finbourne.Sdk.Lusid.Model.FieldValue

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **string** | Required | *No description available.* |
| **Fields** | **Dictionary&lt;string, string&gt;** | Optional | *No description available.* |
| **NumericFields** | **Dictionary&lt;string, decimal&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FieldValue(
    value: "...",  // required
    fields: ,  // optional
    numericFields:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FieldValue>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

