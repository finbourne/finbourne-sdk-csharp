# Finbourne.Sdk.Access.Model.HowSpec

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | *No description available.* |
| **Parameters** | [List&lt;KeyValuePairOfStringToString&gt;](KeyValuePairOfStringToString.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new HowSpec(
    type: "...",  // optional
    parameters: new List<KeyValuePairOfStringToString>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<HowSpec>(json);
```

- [KeyValuePairOfStringToString](KeyValuePairOfStringToString.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

