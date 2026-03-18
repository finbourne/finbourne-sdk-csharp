# Finbourne.Sdk.Lusid.Model.FundDetails

The details of a Fund.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Currency** | **string** | Optional | The currency of the fund which is the same as the base currency of all the portfolios of the fund&#39;s Abor. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundDetails(
    currency: "..."  // optional — The currency of the fund which is the same as the base currency of all the portfolios of the fund&#39;s Abor.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundDetails>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

