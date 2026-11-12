# Finbourne.Sdk.Lusid.Model.BucketAmounts

An amount in the payment currency.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Local** | **decimal** | Optional | The amount in the payment currency. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketAmounts(
    local: 0.0d,  // optional — The amount in the payment currency.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketAmounts>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

