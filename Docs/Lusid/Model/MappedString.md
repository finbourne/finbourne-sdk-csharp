# Finbourne.Sdk.Lusid.Model.MappedString

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LeftValue** | **string** | Optional | *No description available.* |
| **RightValue** | **string** | Optional | *No description available.* |
| **MappingDirection** | **string** | Optional | *No description available.* |
| **IsCaseSensitive** | **bool** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MappedString(
    leftValue: "...",  // optional
    rightValue: "...",  // optional
    mappingDirection: "...",  // optional
    isCaseSensitive: true  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MappedString>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

