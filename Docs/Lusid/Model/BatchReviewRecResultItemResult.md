# Finbourne.Sdk.Lusid.Model.BatchReviewRecResultItemResult

The successful outcome of a single batch review item: every rec result affected by the item (which  may exceed the results named in the request, e.g. group members re-opened by a nullify).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RecResults** | [List&lt;RecResult&gt;](RecResult.md) | Required | The full set of rec results affected by the batch item (may exceed the results named in the request). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchReviewRecResultItemResult(
    recResults: new List<RecResult>()  // required — The full set of rec results affected by the batch item (may exceed the results named in the request).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchReviewRecResultItemResult>(json);
```


## Related Models

- [RecResult](RecResult.md) — used in `RecResults`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

