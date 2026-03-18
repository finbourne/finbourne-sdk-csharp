# Finbourne.Sdk.Lusid.Model.AssetLeg

The underlying instrument representing one side of the TRS and its pay-receive direction.                Note that TRS currently only supports an asset of Bond or ComplexBond, no other instruments are allowed.  Support for additional instrument types will be added in the future.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Asset** | [LusidInstrument](LusidInstrument.md) | Required | *No description available.* |
| **PayReceive** | **string** | Required | Either Pay or Receive stating direction of the asset in the swap.    Supported string (enumeration) values are: [Pay, Receive]. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AssetLeg(
    asset: new LusidInstrument(...),  // required
    payReceive: "..."  // required — Either Pay or Receive stating direction of the asset in the swap.    Supported string (enumeration) values are: [Pay, Receive].
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AssetLeg>(json);
```


## Related Models

- [LusidInstrument](LusidInstrument.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

