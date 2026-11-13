# Finbourne.Sdk.Lusid.Model.ComplianceRuleV3DescribeResponse

A plain-English description of a V3 compliance rule: its identity, the kind of entity it examines, and a  single sentence describing what it checks. The sentence is empty for a rule the generator cannot fully  express.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Subject** | **string** | Optional | Available values: Holdings, Orders. |
| **PlainEnglish** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleV3DescribeResponse(
    id: new ResourceId(...),  // optional
    subject: "...",  // optional — Available values: Holdings, Orders.
    plainEnglish: "..."  // optional
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

