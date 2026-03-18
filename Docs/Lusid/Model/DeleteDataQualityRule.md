# Finbourne.Sdk.Lusid.Model.DeleteDataQualityRule

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleSetKey** | **string** | Optional | *No description available.* |
| **RuleKey** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DeleteDataQualityRule(
    ruleSetKey: "...",  // optional
    ruleKey: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DeleteDataQualityRule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

