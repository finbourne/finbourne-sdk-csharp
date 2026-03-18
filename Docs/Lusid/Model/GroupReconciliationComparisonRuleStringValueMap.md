# Finbourne.Sdk.Lusid.Model.GroupReconciliationComparisonRuleStringValueMap

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LeftValue** | **string** | Required | The left string to map |
| **RightValue** | **string** | Required | The right string to map |
| **Direction** | **string** | Required | The direction to map. \&quot;UniDirectional\&quot; | \&quot;BiDirectional\&quot; |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationComparisonRuleStringValueMap(
    leftValue: "...",  // required — The left string to map
    rightValue: "...",  // required — The right string to map
    direction: "..."  // required — The direction to map. \&quot;UniDirectional\&quot; | \&quot;BiDirectional\&quot;
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationComparisonRuleStringValueMap>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

