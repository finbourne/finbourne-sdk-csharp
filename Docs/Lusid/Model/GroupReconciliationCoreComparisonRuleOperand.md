# Finbourne.Sdk.Lusid.Model.GroupReconciliationCoreComparisonRuleOperand

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | The key of the value to compare |
| **Operation** | **string** | Required | What to do with the value pointed to by the key, e.g. Sum. Only \&quot;Value is allowed for core rules\&quot; |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationCoreComparisonRuleOperand(
    key: "...",  // required — The key of the value to compare
    operation: "..."  // required — What to do with the value pointed to by the key, e.g. Sum. Only \&quot;Value is allowed for core rules\&quot;
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationCoreComparisonRuleOperand>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

