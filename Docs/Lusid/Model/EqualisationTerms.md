# Finbourne.Sdk.Lusid.Model.EqualisationTerms

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Enabled** | **bool** | Required | *No description available.* |
| **InterestRate** | **decimal?** | Optional | *No description available.* |
| **DayCountConvention** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EqualisationTerms(
    enabled: true,  // required
    interestRate: 0.0d,  // optional
    dayCountConvention: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EqualisationTerms>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

