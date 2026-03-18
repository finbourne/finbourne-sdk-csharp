# Finbourne.Sdk.Workflow.Model.ResultMatchingPattern

Standard Finbourne filter to match against Run Worker results
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Filter** | **string** | Required | Filter string |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ResultMatchingPattern(
    filter: "..."  // required — Filter string
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResultMatchingPattern>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

