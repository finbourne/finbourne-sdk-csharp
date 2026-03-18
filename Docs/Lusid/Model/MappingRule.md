# Finbourne.Sdk.Lusid.Model.MappingRule

An individual mapping rule, for mapping between a left and right field/property.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | **string** | Optional | The name of the field/property in the left resource (e.g. a transaction) |
| **Right** | **string** | Optional | The name of the field/property in the right resource (e.g. a transaction) |
| **ComparisonType** | **string** | Optional | The type of comparison to be performed |
| **ComparisonValue** | **decimal?** | Optional | The (optional) value used with ComparisonType. |
| **Weight** | **decimal** | Optional | A factor used to influence the importance of this item. |
| **MappedStrings** | [List&lt;MappedString&gt;](MappedString.md) | Optional | The (optional) value used to map string values. |
| **IsCaseSensitive** | **bool** | Optional | Should string comparisons take case into account, defaults to &#x60;false&#x60;. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MappingRule(
    left: "...",  // optional — The name of the field/property in the left resource (e.g. a transaction)
    right: "...",  // optional — The name of the field/property in the right resource (e.g. a transaction)
    comparisonType: "...",  // optional — The type of comparison to be performed
    comparisonValue: 0.0d,  // optional — The (optional) value used with ComparisonType.
    weight: 0.0d,  // optional — A factor used to influence the importance of this item.
    mappedStrings: new List<MappedString>(),  // optional — The (optional) value used to map string values.
    isCaseSensitive: true  // optional — Should string comparisons take case into account, defaults to &#x60;false&#x60;.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MappingRule>(json);
```

- [MappedString](MappedString.md) — used in `MappedStrings`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

