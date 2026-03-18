# Finbourne.Sdk.Lusid.Model.DialectSchema

A schema that a given document must obey. A representation of the validation of a particular Dialect,  in a given language.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The type of schema this represents |
| **Body** | **string** | Optional | The body of the schema |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DialectSchema(
    type: "...",  // required — The type of schema this represents
    body: "..."  // optional — The body of the schema
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DialectSchema>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

