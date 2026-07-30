# Finbourne.Sdk.Lusid.Model.RecResultCounts

Counts of results broken down by the structural categories that align with the review configuration.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OpenExceptions** | [RecOpenExceptionCounts](RecOpenExceptionCounts.md) | Required | *No description available.* |
| **ClosedExceptions** | [RecClosedExceptionCounts](RecClosedExceptionCounts.md) | Required | *No description available.* |
| **Matches** | [RecMatchCounts](RecMatchCounts.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultCounts(
    openExceptions: new RecOpenExceptionCounts(...),  // required
    closedExceptions: new RecClosedExceptionCounts(...),  // required
    matches: new RecMatchCounts(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultCounts>(json);
```


## Related Models

- [RecOpenExceptionCounts](RecOpenExceptionCounts.md)
- [RecClosedExceptionCounts](RecClosedExceptionCounts.md)
- [RecMatchCounts](RecMatchCounts.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

