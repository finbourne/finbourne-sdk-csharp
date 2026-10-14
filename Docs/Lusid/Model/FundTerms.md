# Finbourne.Sdk.Lusid.Model.FundTerms

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Versions** | [List&lt;FundTermsVersion&gt;](FundTermsVersion.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundTerms(
    versions: new List<FundTermsVersion>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundTerms>(json);
```


## Related Models

- [FundTermsVersion](FundTermsVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

