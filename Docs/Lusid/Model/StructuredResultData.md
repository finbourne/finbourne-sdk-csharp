# Finbourne.Sdk.Lusid.Model.StructuredResultData

An item of structured result data that is to be inserted into Lusid. This will typically be a Json or Xml document that  contains a set of result data appropriate to a specific entity such as an instrument or potentially an index.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DocumentFormat** | **string** | Required | The format of the accompanying document. |
| **VarVersion** | **string** | Optional | The semantic version of the document format; MAJOR.MINOR.PATCH |
| **Name** | **string** | Optional | The name or description for the document |
| **Document** | **string** | Required | The document that will be stored (or retrieved) and which describes a unit result data entity such as a set of prices or yields |
| **DataMapKey** | [DataMapKey](DataMapKey.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StructuredResultData(
    documentFormat: "...",  // required — The format of the accompanying document.
    varVersion: "...",  // optional — The semantic version of the document format; MAJOR.MINOR.PATCH
    name: "...",  // optional — The name or description for the document
    document: "...",  // required — The document that will be stored (or retrieved) and which describes a unit result data entity such as a set of prices or yields
    dataMapKey: new DataMapKey(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StructuredResultData>(json);
```

- [DataMapKey](DataMapKey.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

