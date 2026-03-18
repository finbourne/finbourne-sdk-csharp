# Finbourne.Sdk.Lusid.Model.LineageMember

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Index** | **int** | Required | Index to demonstrate position of lineage member in overall lineage |
| **Label** | **string** | Required | Label of the step corresponding to this lineage member |
| **SubLabel** | **string** | Required | SubLabel of the step corresponding to this lineage member |
| **InfoType** | **string** | Optional | Optional. Type of Information |
| **Information** | **string** | Optional | Optional. Information for the step corresponding to this lineage member, of type InfoType |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new LineageMember(
    index: 0,  // required — Index to demonstrate position of lineage member in overall lineage
    label: "...",  // required — Label of the step corresponding to this lineage member
    subLabel: "...",  // required — SubLabel of the step corresponding to this lineage member
    infoType: "...",  // optional — Optional. Type of Information
    information: "..."  // optional — Optional. Information for the step corresponding to this lineage member, of type InfoType
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LineageMember>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

