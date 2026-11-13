# Finbourne.Sdk.Lusid.Model.ComplianceKeyUsed

A key a holding contributed to the rule: the key, the role(s) it played in the rule, the holding's own value for  it, and which bag the value was read from.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | *No description available.* |
| **Roles** | **List&lt;string&gt;** | Required | *No description available.* |
| **Value** | **Object** | Optional | This holding&#39;s own value for the key. Polymorphic: a number for a result or metric property, a label string for  a label property, or a string for a related property. |
| **Source** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceKeyUsed(
    key: "...",  // required
    roles: ,  // required
    value: ,  // optional — This holding&#39;s own value for the key. Polymorphic: a number for a result or metric property, a label string for  a label property, or a string for a related property.
    source: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceKeyUsed>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

