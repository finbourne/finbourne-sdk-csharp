# Finbourne.Sdk.Lusid.Model.KeyedMarketDataKeyRule

One keyed rule of an MdkrGroup shift: the key names the result column (scenario:key) and the rule  is a standard market data key rule resolved for that column.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | The key naming this rule&#39;s result column, e.g. \&quot;bid\&quot;. |
| **Rule** | [MarketDataKeyRule](MarketDataKeyRule.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new KeyedMarketDataKeyRule(
    key: "...",  // required — The key naming this rule&#39;s result column, e.g. \&quot;bid\&quot;.
    rule: new MarketDataKeyRule(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<KeyedMarketDataKeyRule>(json);
```

- [MarketDataKeyRule](MarketDataKeyRule.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

