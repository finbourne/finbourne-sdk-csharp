# Finbourne.Sdk.Lusid.Model.SupplementalAttributeValues

A supplemental attribute value carried on a rec result for context. Does not contribute to matching.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AttributeName** | **string** | Required | The name of the supplemental attribute. |
| **LeftValue** | **string** | Optional | The left-side value: the value the left items agree on, or \&quot;[multiple values]\&quot; where they do not. Null where the left side has no items. |
| **RightValue** | **string** | Optional | The right-side value: the value the right items agree on, or \&quot;[multiple values]\&quot; where they do not. Null where the right side has no items. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SupplementalAttributeValues(
    attributeName: "...",  // required — The name of the supplemental attribute.
    leftValue: "...",  // optional — The left-side value: the value the left items agree on, or \&quot;[multiple values]\&quot; where they do not. Null where the left side has no items.
    rightValue: "..."  // optional — The right-side value: the value the right items agree on, or \&quot;[multiple values]\&quot; where they do not. Null where the right side has no items.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SupplementalAttributeValues>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

