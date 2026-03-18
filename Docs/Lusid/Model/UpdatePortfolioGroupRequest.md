# Finbourne.Sdk.Lusid.Model.UpdatePortfolioGroupRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The name of the portfolio group. |
| **Description** | **string** | Optional | A long form description of the portfolio group. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdatePortfolioGroupRequest(
    displayName: "...",  // required — The name of the portfolio group.
    description: "..."  // optional — A long form description of the portfolio group.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdatePortfolioGroupRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

