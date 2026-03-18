# Finbourne.Sdk.Configuration.Model.CreateConfigurationItem

The information required to create a configuration item
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | The key of the new configuration item |
| **Value** | **string** | Required | The value of the new configuration item              The maximum size for secrets is 4KB and for text values is 2MB |
| **ValueType** | **string** | Optional | The type (text, number, boolean, textCollection, numberCollection) of the new configuration item&#39;s value. The validation for each type is as follows: - text: any value - number: double (e.g. \&quot;5.5\&quot;) - boolean: true/false - textCollection: comma separated list (e.g. \&quot;a,b,c\&quot;) - numberCollection: comma separated list of doubles (e.g. \&quot;1,2,3\&quot;) |
| **IsSecret** | **bool** | Required | Defines whether or not the value is a secret |
| **Description** | **string** | Optional | The description of the new configuration item |
| **BlockReveal** | **bool** | Optional | A property to indicate if revealing the value is blocked. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Configuration.Model;

var instance = new CreateConfigurationItem(
    key: "...",  // required — The key of the new configuration item
    value: "...",  // required — The value of the new configuration item              The maximum size for secrets is 4KB and for text values is 2MB
    valueType: "...",  // optional — The type (text, number, boolean, textCollection, numberCollection) of the new configuration item&#39;s value. The validation for each type is as follows: - text: any value - number: double (e.g. \&quot;5.5\&quot;) - boolean: true/false - textCollection: comma separated list (e.g. \&quot;a,b,c\&quot;) - numberCollection: comma separated list of doubles (e.g. \&quot;1,2,3\&quot;)
    isSecret: true,  // required — Defines whether or not the value is a secret
    description: "...",  // optional — The description of the new configuration item
    blockReveal: true  // optional — A property to indicate if revealing the value is blocked.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateConfigurationItem>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

