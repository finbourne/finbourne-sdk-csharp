# Finbourne.Sdk.Horizon.Model.TpfRetryElementResult

Result for a single batch element retry attempt
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BatchElementReferenceId** | **string** | Required | Batch element reference identifier |
| **Status** | **string** | Required | Status of the retry attempt (e.g., \&quot;Retrying\&quot;, \&quot;NotFound\&quot;) |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new TpfRetryElementResult(
    batchElementReferenceId: "...",  // required — Batch element reference identifier
    status: "..."  // required — Status of the retry attempt (e.g., \&quot;Retrying\&quot;, \&quot;NotFound\&quot;)
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TpfRetryElementResult>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

