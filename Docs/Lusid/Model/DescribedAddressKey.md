# Finbourne.Sdk.Lusid.Model.DescribedAddressKey

An address key with additional data describing what this key is for.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AddressKey** | **string** | Optional | Address key of some underlying object e.g. Valuation/PV, Instrument/Features |
| **Description** | **string** | Optional | Description of the address key. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DescribedAddressKey(
    addressKey: "...",  // optional — Address key of some underlying object e.g. Valuation/PV, Instrument/Features
    description: "..."  // optional — Description of the address key.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DescribedAddressKey>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

