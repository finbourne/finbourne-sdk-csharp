# Finbourne.Sdk.Lusid.Model.MarginRounding

The increment margin calls are rounded to, and the direction for deliveries and returns.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Amount** | **decimal** | Required | The increment margin calls are rounded to. Must be greater than zero. |
| **Deliveries** | **string** | Required | How amounts we deliver are rounded. One of Up or Nearest. Available values: Up, Down, Nearest. |
| **Returns** | **string** | Required | How amounts we receive back are rounded. One of Down or Nearest. Available values: Up, Down, Nearest. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarginRounding(
    amount: 0.0d,  // required — The increment margin calls are rounded to. Must be greater than zero.
    deliveries: "...",  // required — How amounts we deliver are rounded. One of Up or Nearest. Available values: Up, Down, Nearest.
    returns: "..."  // required — How amounts we receive back are rounded. One of Down or Nearest. Available values: Up, Down, Nearest.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarginRounding>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

