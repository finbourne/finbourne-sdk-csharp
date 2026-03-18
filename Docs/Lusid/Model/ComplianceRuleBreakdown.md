# Finbourne.Sdk.Lusid.Model.ComplianceRuleBreakdown

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **GroupStatus** | **string** | Required | The status of this subset of results. |
| **ResultsUsed** | **Dictionary&lt;string, decimal&gt;** | Required | Dictionary of AddressKey (as string) and their corresponding decimal values, that were used in this rule. |
| **PropertiesUsed** | **Dictionary&lt;string, List&lt;Property&gt;&gt;** | Required | Dictionary of PropertyKey (as string) and their corresponding Properties, that were used in this rule |
| **MissingDataInformation** | **List&lt;string&gt;** | Required | List of string information detailing data that was missing from contributions processed in this rule |
| **Lineage** | [List&lt;LineageMember&gt;](LineageMember.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleBreakdown(
    groupStatus: "...",  // required — The status of this subset of results.
    resultsUsed: ,  // required — Dictionary of AddressKey (as string) and their corresponding decimal values, that were used in this rule.
    propertiesUsed: ,  // required — Dictionary of PropertyKey (as string) and their corresponding Properties, that were used in this rule
    missingDataInformation: ,  // required — List of string information detailing data that was missing from contributions processed in this rule
    lineage: new List<LineageMember>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleBreakdown>(json);
```

- [LineageMember](LineageMember.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

