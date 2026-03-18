# Finbourne.Sdk.Lusid.Model.ResponseMetaData

Metadata related to an api response
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | The type of meta data information being provided |
| **Description** | **string** | Optional | The description of what occured for this specific piece of meta data |
| **IdentifierType** | **string** | Optional | The type of the listed identifiers |
| **Identifiers** | **List&lt;string&gt;** | Optional | The related identifiers that were impacted by this event |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ResponseMetaData(
    type: "...",  // optional — The type of meta data information being provided
    description: "...",  // optional — The description of what occured for this specific piece of meta data
    identifierType: "...",  // optional — The type of the listed identifiers
    identifiers:   // optional — The related identifiers that were impacted by this event
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResponseMetaData>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

