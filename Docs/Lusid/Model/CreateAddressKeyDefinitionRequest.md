# Finbourne.Sdk.Lusid.Model.CreateAddressKeyDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AddressKey** | **string** | Required | The address key of the address key definition. |
| **Type** | **string** | Required | The type of the address key definition |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateAddressKeyDefinitionRequest(
    addressKey: "...",  // required — The address key of the address key definition.
    type: "..."  // required — The type of the address key definition
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateAddressKeyDefinitionRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

