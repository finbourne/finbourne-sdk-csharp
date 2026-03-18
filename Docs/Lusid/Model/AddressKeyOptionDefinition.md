# Finbourne.Sdk.Lusid.Model.AddressKeyOptionDefinition

The definition of an Address Key Option
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name of the option |
| **Type** | **string** | Required | The type of the option |
| **Description** | **string** | Required | The description of the option |
| **Optional** | **bool** | Required | Is this option required or optional? |
| **AllowedValueSet** | **List&lt;string&gt;** | Optional | If the option is a string or enum, the allowed set of values it can take. |
| **DefaultValue** | **string** | Optional | If the option is not required, what is the default value? |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AddressKeyOptionDefinition(
    name: "...",  // required — The name of the option
    type: "...",  // required — The type of the option
    description: "...",  // required — The description of the option
    optional: true,  // required — Is this option required or optional?
    allowedValueSet: ,  // optional — If the option is a string or enum, the allowed set of values it can take.
    defaultValue: "..."  // optional — If the option is not required, what is the default value?
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AddressKeyOptionDefinition>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

