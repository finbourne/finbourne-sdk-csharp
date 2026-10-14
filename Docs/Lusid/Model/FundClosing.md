# Finbourne.Sdk.Lusid.Model.FundClosing

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ClosingId** | **string** | Required | *No description available.* |
| **ClosingDate** | **DateTimeOffset** | Required | *No description available.* |
| **IsFinal** | **bool?** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundClosing(
    closingId: "...",  // required
    closingDate: DateTimeOffset.Now,  // required
    isFinal: true,  // optional
    description: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundClosing>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

