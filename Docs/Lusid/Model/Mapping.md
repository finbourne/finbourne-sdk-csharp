# Finbourne.Sdk.Lusid.Model.Mapping

Defines the rule set to be used to determine if entries should be considered as a match.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope for this mapping. |
| **Code** | **string** | Required | The code for this mapping. |
| **Name** | **string** | Required | The mapping name |
| **ReconciliationType** | **string** | Required | What type of reconciliation this mapping is for |
| **Rules** | [List&lt;MappingRule&gt;](MappingRule.md) | Optional | The rules in this mapping, keyed by the left field/property name |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Mapping(
    scope: "...",  // required — The scope for this mapping.
    code: "...",  // required — The code for this mapping.
    name: "...",  // required — The mapping name
    reconciliationType: "...",  // required — What type of reconciliation this mapping is for
    rules: new List<MappingRule>()  // optional — The rules in this mapping, keyed by the left field/property name
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Mapping>(json);
```

- [MappingRule](MappingRule.md) — used in `Rules`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

