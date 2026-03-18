# Finbourne.Sdk.Horizon.Model.IntegrationRunLog

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Count** | **long** | Required | *No description available.* |
| **Link** | [IntegrationRunLogLink](IntegrationRunLogLink.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new IntegrationRunLog(
    count: 0L,  // required
    link: new IntegrationRunLogLink(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IntegrationRunLog>(json);
```

- [IntegrationRunLogLink](IntegrationRunLogLink.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

