# Finbourne.Sdk.Lusid.Model.ComplianceRuleBreakdownRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **GroupStatus** | **string** | Required | *No description available.* |
| **ResultsUsed** | **Dictionary&lt;string, decimal&gt;** | Required | *No description available.* |
| **PropertiesUsed** | **Dictionary&lt;string, List&lt;Property&gt;&gt;** | Required | *No description available.* |
| **MissingDataInformation** | **List&lt;string&gt;** | Required | *No description available.* |
| **Lineage** | [List&lt;LineageMember&gt;](LineageMember.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleBreakdownRequest(
    groupStatus: "...",  // required
    resultsUsed: ,  // required
    propertiesUsed: ,  // required
    missingDataInformation: ,  // required
    lineage: new List<LineageMember>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleBreakdownRequest>(json);
```

- [LineageMember](LineageMember.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

