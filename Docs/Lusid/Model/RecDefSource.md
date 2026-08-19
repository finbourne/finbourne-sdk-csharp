# Finbourne.Sdk.Lusid.Model.RecDefSource

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SourceType** | **string** | Required | The type of entity that this source refers to. One of: Portfolio, PortfolioGroup, Fund. Available values: Portfolio, PortfolioGroup, Fund. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecDefSource(
    sourceType: "...",  // required — The type of entity that this source refers to. One of: Portfolio, PortfolioGroup, Fund. Available values: Portfolio, PortfolioGroup, Fund.
    id: new ResourceId(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecDefSource>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

