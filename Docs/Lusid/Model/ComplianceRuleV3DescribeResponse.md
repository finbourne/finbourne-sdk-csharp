# Finbourne.Sdk.Lusid.Model.ComplianceRuleV3DescribeResponse

A plain-English description of a V3 compliance rule. This is a minimal placeholder shape: the plain-English  generator is delivered separately, so the Lines property is currently empty and only the rule's identity  and subject are populated.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Subject** | **string** | Optional | Available values: Holdings, Orders. |
| **Lines** | **List&lt;string&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleV3DescribeResponse(
    id: new ResourceId(...),  // optional
    subject: "...",  // optional — Available values: Holdings, Orders.
    lines:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleV3DescribeResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

