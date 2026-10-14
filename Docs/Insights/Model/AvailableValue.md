# Finbourne.Sdk.Insights.Model.AvailableValue

A value known to be valid for a queryable log field, which a UI can offer when filtering on that field.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **string** | Required | The value. |
| **Context** | **string** | Optional | Optional context qualifying the value. For the Operation field this is the comma-separated names of the applications that publish the operation. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new AvailableValue(
    value: "...",  // required — The value.
    context: "..."  // optional — Optional context qualifying the value. For the Operation field this is the comma-separated names of the applications that publish the operation.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AvailableValue>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

