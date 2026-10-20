# Finbourne.Sdk.Lusid.Model.AcceptMarginCallRequest

Accepts a margin call, at its default agreed amount or the amount given.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AgreedAmount** | **decimal?** | Optional | The amount to accept. Optional when the call is matched or within tolerance, when our call or the counterparty&#39;s demand is taken; required when the demand breaks tolerance or has not been recorded. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AcceptMarginCallRequest(
    agreedAmount: 0.0d  // optional — The amount to accept. Optional when the call is matched or within tolerance, when our call or the counterparty&#39;s demand is taken; required when the demand breaks tolerance or has not been recorded.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AcceptMarginCallRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

