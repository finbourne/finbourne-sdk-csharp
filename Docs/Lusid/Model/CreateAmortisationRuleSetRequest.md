# Finbourne.Sdk.Lusid.Model.CreateAmortisationRuleSetRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | *No description available.* |
| **DisplayName** | **string** | Required | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateAmortisationRuleSetRequest(
    code: "...",  // required
    displayName: "...",  // required
    description: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateAmortisationRuleSetRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

