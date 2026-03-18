# Finbourne.Sdk.Lusid.Model.QuantityInstructed

The quantity of the event that was instructed, represented either as a percentage of the overall holdings or the number of units instructed.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The type of quantity instructed, either Percentage or Units. |
| **Amount** | **decimal** | Required | The actual amount instructed. For Type Percentage, this is between 0 and 100. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QuantityInstructed(
    type: "...",  // required — The type of quantity instructed, either Percentage or Units.
    amount: 0.0d  // required — The actual amount instructed. For Type Percentage, this is between 0 and 100.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QuantityInstructed>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

