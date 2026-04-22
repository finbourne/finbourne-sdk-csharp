# Finbourne.Sdk.Horizon.Model.ClientConfigurationResponse

Represents a versioned client configuration record.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The logical name of the configuration. |
| **ConfigType** | **string** | Required | The category of configuration. |
| **MajorVersion** | **int** | Required | The major version number. |
| **MinorVersion** | **int** | Required | The minor version number. |
| **Value** | **string** | Required | The JSON configuration value. |
| **IsDraft** | **bool** | Required | Whether this version is still in draft state. Draft versions can be edited; locked versions cannot. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new ClientConfigurationResponse(
    name: "...",  // required — The logical name of the configuration.
    configType: "...",  // required — The category of configuration.
    majorVersion: 0,  // required — The major version number.
    minorVersion: 0,  // required — The minor version number.
    value: "...",  // required — The JSON configuration value.
    isDraft: true  // required — Whether this version is still in draft state. Draft versions can be edited; locked versions cannot.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ClientConfigurationResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

