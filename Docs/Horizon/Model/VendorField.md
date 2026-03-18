# Finbourne.Sdk.Horizon.Model.VendorField

Reference to a specific vendor field
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Package** | **string** | Required | The vendor package it is included in |
| **Field** | **string** | Required | The name of the field |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new VendorField(
    package: "...",  // required — The vendor package it is included in
    field: "..."  // required — The name of the field
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VendorField>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

