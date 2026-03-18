# Finbourne.Sdk.Horizon.Model.LusidField

A field on a LUSID entity
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FieldName** | **string** | Required | The name of the LUSID field. |
| **DefaultValue** | **string** | Optional | The default value for the field. |
| **VendorPackages** | **List&lt;string&gt;** | Required | The vendor package that contributes to this LUSID field. |
| **VendorNamespaces** | **List&lt;string&gt;** | Required | The vendor namespace that contributes to this LUSID field. |
| **VendorFields** | **List&lt;string&gt;** | Required | The underlying fields on the vendor package that contribute to this LUSID field |
| **TransformationDescription** | **string** | Optional | A description of how the vendor package&#39;s field(s) get mapped to the LUSID field |
| **EntityType** | **string** | Required | LUSID Entity this refers to (e.g. Instrument) |
| **EntitySubType** | **string** | Optional | Sub-Entity this field refers to (e.g. Equity) |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new LusidField(
    fieldName: "...",  // required — The name of the LUSID field.
    defaultValue: "...",  // optional — The default value for the field.
    vendorPackages: ,  // required — The vendor package that contributes to this LUSID field.
    vendorNamespaces: ,  // required — The vendor namespace that contributes to this LUSID field.
    vendorFields: ,  // required — The underlying fields on the vendor package that contribute to this LUSID field
    transformationDescription: "...",  // optional — A description of how the vendor package&#39;s field(s) get mapped to the LUSID field
    entityType: "...",  // required — LUSID Entity this refers to (e.g. Instrument)
    entitySubType: "..."  // optional — Sub-Entity this field refers to (e.g. Equity)
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LusidField>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

