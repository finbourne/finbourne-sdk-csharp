# Finbourne.Sdk.Lusid.Model.BatchAcceptMarginCallsRequest

Accepts several margin calls at their default agreed amounts, reporting the ones that could not be accepted.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Calls** | [List&lt;MarginCallKey&gt;](MarginCallKey.md) | Required | The calls to accept, each at its default agreed amount. A call that cannot be accepted is reported in failed and does not stop the others. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchAcceptMarginCallsRequest(
    calls: new List<MarginCallKey>()  // required — The calls to accept, each at its default agreed amount. A call that cannot be accepted is reported in failed and does not stop the others.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchAcceptMarginCallsRequest>(json);
```


## Related Models

- [MarginCallKey](MarginCallKey.md) — used in `Calls`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

