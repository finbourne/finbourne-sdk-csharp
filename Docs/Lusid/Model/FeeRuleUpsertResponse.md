# Finbourne.Sdk.Lusid.Model.FeeRuleUpsertResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [Dictionary&lt;string, FeeRule&gt;](FeeRule.md) | Required | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FeeRuleUpsertResponse(
    values: new FeeRule(...),  // required
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FeeRuleUpsertResponse>(json);
```


## Related Models

- [FeeRule](FeeRule.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

