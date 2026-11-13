# Finbourne.Sdk.Lusid.Model.ElectionProrationRate

The proration rate the issuer applies to one option of a multi-option event, keyed by the option's election key.  An entry overrides the event-level proration rate for that election only.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ElectionKey** | **string** | Required | The election key of the option this proration rate applies to. |
| **ProrationRate** | **decimal** | Required | The fraction of the quantity instructed on this option that the issuer accepts. Must be in (0, 1]. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ElectionProrationRate(
    electionKey: "...",  // required — The election key of the option this proration rate applies to.
    prorationRate: 0.0d  // required — The fraction of the quantity instructed on this option that the issuer accepts. Must be in (0, 1].
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ElectionProrationRate>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

