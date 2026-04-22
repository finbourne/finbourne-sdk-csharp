# Finbourne.Sdk.Horizon.Model.CreateClientConfigurationDraftRequest

Request to create a new draft client configuration.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MajorVersion** | **int?** | Optional | The major version for the new draft. Must be supplied together with minorVersion, or both omitted to auto-assign the next version. |
| **MinorVersion** | **int?** | Optional | The minor version for the new draft. Must be supplied together with MajorVersion, or both omitted to auto-assign the next version. |
| **SourceMajorVersion** | **int?** | Optional | The major version of an existing record to copy the value from. Must be supplied together with SourceMinorVersion. If omitted, the new draft is initialised with an empty JSON object. |
| **SourceMinorVersion** | **int?** | Optional | The minor version of an existing record to copy the value from. Must be supplied together with SourceMajorVersion. If omitted, the new draft is initialised with an empty JSON object. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new CreateClientConfigurationDraftRequest(
    majorVersion: 0,  // optional — The major version for the new draft. Must be supplied together with minorVersion, or both omitted to auto-assign the next version.
    minorVersion: 0,  // optional — The minor version for the new draft. Must be supplied together with MajorVersion, or both omitted to auto-assign the next version.
    sourceMajorVersion: 0,  // optional — The major version of an existing record to copy the value from. Must be supplied together with SourceMinorVersion. If omitted, the new draft is initialised with an empty JSON object.
    sourceMinorVersion: 0  // optional — The minor version of an existing record to copy the value from. Must be supplied together with SourceMajorVersion. If omitted, the new draft is initialised with an empty JSON object.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateClientConfigurationDraftRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

