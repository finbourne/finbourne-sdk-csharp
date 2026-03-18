# Finbourne.Sdk.Lusid.Model.RoundingConfigurationComponent

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RoundingType** | **string** | Required | The type of rounding that should be used, eg: Up, Down, NearestRoundHalfAwayFromZero |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RoundingConfigurationComponent(
    roundingType: "..."  // required — The type of rounding that should be used, eg: Up, Down, NearestRoundHalfAwayFromZero
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RoundingConfigurationComponent>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

