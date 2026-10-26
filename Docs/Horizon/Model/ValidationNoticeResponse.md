# Finbourne.Sdk.Horizon.Model.ValidationNoticeResponse

A non-blocking finding raised when an instance was saved. The save succeeded regardless.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Severity** | **string** | Required | \&quot;Warning\&quot; or \&quot;Information\&quot;. |
| **Field** | **string** | Required | The configuration field the finding relates to. |
| **Message** | **string** | Required | What was found. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new ValidationNoticeResponse(
    severity: "...",  // required — \&quot;Warning\&quot; or \&quot;Information\&quot;.
    field: "...",  // required — The configuration field the finding relates to.
    message: "..."  // required — What was found.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ValidationNoticeResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

