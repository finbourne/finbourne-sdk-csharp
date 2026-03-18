# Finbourne.Sdk.Lusid.Model.StagingRuleMatchCriteria

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ActionIn** | **List&lt;string&gt;** | Optional | *No description available.* |
| **RequestingUser** | **string** | Optional | *No description available.* |
| **EntityAttributes** | **string** | Optional | *No description available.* |
| **ChangedAttributeNameIn** | **List&lt;string&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StagingRuleMatchCriteria(
    actionIn: ,  // optional
    requestingUser: "...",  // optional
    entityAttributes: "...",  // optional
    changedAttributeNameIn:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StagingRuleMatchCriteria>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

