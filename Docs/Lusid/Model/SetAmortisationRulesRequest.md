# Finbourne.Sdk.Lusid.Model.SetAmortisationRulesRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RulesInterval** | [RulesInterval](RulesInterval.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SetAmortisationRulesRequest(
    rulesInterval: new RulesInterval(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SetAmortisationRulesRequest>(json);
```


## Related Models

- [RulesInterval](RulesInterval.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

