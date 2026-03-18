# Finbourne.Sdk.Horizon.Model.LusidPropertyDefinitionOverridesResponse

An item that has been updated as a result of setting LusidPropertyDefinitionOverrides.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Action** | **string** | Required | The action performed on this property. \&quot;upsert\&quot; for setting values for new and existing             properties. \&quot;delete\&quot; for existing properties that were removed |
| **WriteError** | **string** | Optional | *No description available.* |
| **WriteErrorDetail** | **string** | Optional | *No description available.* |
| **DisplayNameOverride** | **string** | Optional | *No description available.* |
| **DescriptionOverride** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new LusidPropertyDefinitionOverridesResponse(
    action: "...",  // required — The action performed on this property. \&quot;upsert\&quot; for setting values for new and existing             properties. \&quot;delete\&quot; for existing properties that were removed
    writeError: "...",  // optional
    writeErrorDetail: "...",  // optional
    displayNameOverride: "...",  // optional
    descriptionOverride: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LusidPropertyDefinitionOverridesResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

