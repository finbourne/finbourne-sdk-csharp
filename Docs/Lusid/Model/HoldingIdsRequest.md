# Finbourne.Sdk.Lusid.Model.HoldingIdsRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **HoldingIds** | **List&lt;long&gt;** | Required | The array of unique holding identifiers |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new HoldingIdsRequest(
    holdingIds:   // required — The array of unique holding identifiers
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<HoldingIdsRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

