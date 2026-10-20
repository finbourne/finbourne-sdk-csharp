# Finbourne.Sdk.Lusid.Model.DisputeMarginCallRequest

Disputes a margin call: moves the agreed amount now and leaves the rest of the demand in dispute.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AgreedAmount** | **decimal** | Required | The amount to move now; the rest of the counterparty&#39;s demand is left in dispute. |
| **Reason** | **string** | Required | Why the call is disputed. |
| **Owner** | **string** | Optional | Who owns the dispute. Defaults to the caller if not specified. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DisputeMarginCallRequest(
    agreedAmount: 0.0d,  // required — The amount to move now; the rest of the counterparty&#39;s demand is left in dispute.
    reason: "...",  // required — Why the call is disputed.
    owner: "..."  // optional — Who owns the dispute. Defaults to the caller if not specified.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DisputeMarginCallRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

