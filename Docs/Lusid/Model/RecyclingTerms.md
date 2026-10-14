# Finbourne.Sdk.Lusid.Model.RecyclingTerms

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Enabled** | **bool** | Required | *No description available.* |
| **CapPercentageOfCommitments** | **decimal?** | Optional | *No description available.* |
| **RecyclingEndDate** | **DateTimeOffset?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecyclingTerms(
    enabled: true,  // required
    capPercentageOfCommitments: 0.0d,  // optional
    recyclingEndDate: DateTimeOffset.Now  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecyclingTerms>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

