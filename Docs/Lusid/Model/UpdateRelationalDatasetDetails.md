# Finbourne.Sdk.Lusid.Model.UpdateRelationalDatasetDetails

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | A user-friendly display name for the relational dataset definition. |
| **Description** | **string** | Optional | A detailed description of the relational dataset definition and its purpose. |
| **ApplicableEntityTypes** | [ApplicableEntityTypes](ApplicableEntityTypes.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateRelationalDatasetDetails(
    displayName: "...",  // required — A user-friendly display name for the relational dataset definition.
    description: "...",  // optional — A detailed description of the relational dataset definition and its purpose.
    applicableEntityTypes: new ApplicableEntityTypes(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateRelationalDatasetDetails>(json);
```

- [ApplicableEntityTypes](ApplicableEntityTypes.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

