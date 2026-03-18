# Finbourne.Sdk.Lusid.Model.IndustryClassifier

Object describing a particular industry classifier,  which comprises a classification code and the name of the classification system to which the code belongs.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ClassificationSystemName** | **string** | Required | The name of the classification system to which the classification code belongs (e.g. GICS). |
| **ClassificationCode** | **string** | Required | The specific industry classification code assigned to the legal entity. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new IndustryClassifier(
    classificationSystemName: "...",  // required — The name of the classification system to which the classification code belongs (e.g. GICS).
    classificationCode: "..."  // required — The specific industry classification code assigned to the legal entity.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IndustryClassifier>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

