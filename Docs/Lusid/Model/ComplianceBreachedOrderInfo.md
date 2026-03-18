# Finbourne.Sdk.Lusid.Model.ComplianceBreachedOrderInfo

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OrderId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **ListRuleResult** | [List&lt;ComplianceRuleResult&gt;](ComplianceRuleResult.md) | Required | The Rule Results for a particular compliance run |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceBreachedOrderInfo(
    orderId: new ResourceId(...),  // required
    listRuleResult: new List<ComplianceRuleResult>()  // required — The Rule Results for a particular compliance run
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceBreachedOrderInfo>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ComplianceRuleResult](ComplianceRuleResult.md) — used in `ListRuleResult`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

