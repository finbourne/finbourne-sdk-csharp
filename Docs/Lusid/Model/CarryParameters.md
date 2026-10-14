# Finbourne.Sdk.Lusid.Model.CarryParameters

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CarryRate** | **decimal** | Required | *No description available.* |
| **PreferredReturnRate** | **decimal?** | Optional | *No description available.* |
| **CatchUpRate** | **decimal?** | Optional | *No description available.* |
| **WaterfallType** | **string** | Optional | Available values: WholeOfFund, DealByDeal. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CarryParameters(
    carryRate: 0.0d,  // required
    preferredReturnRate: 0.0d,  // optional
    catchUpRate: 0.0d,  // optional
    waterfallType: "..."  // optional — Available values: WholeOfFund, DealByDeal.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CarryParameters>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

