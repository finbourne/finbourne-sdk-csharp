# Finbourne.Sdk.Lusid.Model.DateAttributes

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Irregular** | **bool** | Required | *No description available.* |
| **IrregularSession** | **bool** | Required | *No description available.* |
| **NewHours** | **bool** | Required | *No description available.* |
| **Activity** | **string** | Optional | *No description available.* |
| **FirstOpen** | **string** | Optional | *No description available.* |
| **LastOpen** | **string** | Optional | *No description available.* |
| **FirstClose** | **string** | Optional | *No description available.* |
| **LastClose** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DateAttributes(
    irregular: true,  // required
    irregularSession: true,  // required
    newHours: true,  // required
    activity: "...",  // optional
    firstOpen: "...",  // optional
    lastOpen: "...",  // optional
    firstClose: "...",  // optional
    lastClose: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DateAttributes>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

