# Finbourne.Sdk.Lusid.Model.UpdatePortfolioRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The name of the transaction portfolio. |
| **Description** | **string** | Optional | The description of the transaction portfolio. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdatePortfolioRequest(
    displayName: "...",  // required — The name of the transaction portfolio.
    description: "..."  // optional — The description of the transaction portfolio.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdatePortfolioRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

