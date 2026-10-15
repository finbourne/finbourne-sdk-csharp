# Finbourne.Sdk.Lusid.Model.PresentationConfiguration

How partner capital is presented on statements and the valuation point.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ContributionsReceivableNetted** | **bool?** | Optional | *No description available.* |
| **SeparateNoticeDueReceiptDates** | **bool?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PresentationConfiguration(
    contributionsReceivableNetted: true,  // optional
    separateNoticeDueReceiptDates: true  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PresentationConfiguration>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

