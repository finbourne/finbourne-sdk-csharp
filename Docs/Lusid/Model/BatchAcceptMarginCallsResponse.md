# Finbourne.Sdk.Lusid.Model.BatchAcceptMarginCallsResponse

The outcome of accepting several margin calls: those accepted, and those refused with the reason.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [List&lt;MarginCall&gt;](MarginCall.md) | Required | The calls that were accepted. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Required | The calls that could not be accepted, keyed by call id, with the reason. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchAcceptMarginCallsResponse(
    values: new List<MarginCall>(),  // required — The calls that were accepted.
    failed: new ErrorDetail(...)  // required — The calls that could not be accepted, keyed by call id, with the reason.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchAcceptMarginCallsResponse>(json);
```


## Related Models

- [MarginCall](MarginCall.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

