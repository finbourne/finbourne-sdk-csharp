# Finbourne.Sdk.Access.Model.AsAtPredicateContract

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **string** | Optional | *No description available.* |
| **DateTimeOffset** | **DateTimeOffset?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new AsAtPredicateContract(
    value: "...",  // optional
    dateTimeOffset: DateTimeOffset.Now  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AsAtPredicateContract>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

