# Finbourne.Sdk.Workflow.Model.Worker

Information about the Worker
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | Human readable name |
| **Description** | **string** | Optional | Human readable description |
| **WorkerConfiguration** | [WorkerConfigurationResponse](WorkerConfigurationResponse.md) | Required | *No description available.* |
| **VarVersion** | [VersionInfo](VersionInfo.md) | Optional | *No description available.* |
| **Parameters** | [List&lt;Parameter&gt;](Parameter.md) | Optional | The Parameters this Worker accepts or requires. |
| **ResultFields** | [List&lt;ResultField&gt;](ResultField.md) | Optional | The Fields that the Worker results will come back with. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new Worker(
    id: new ResourceId(...),  // required
    displayName: "...",  // required — Human readable name
    description: "...",  // optional — Human readable description
    workerConfiguration: new WorkerConfigurationResponse(...),  // required
    varVersion: new VersionInfo(...),  // optional
    parameters: new List<Parameter>(),  // optional — The Parameters this Worker accepts or requires.
    resultFields: new List<ResultField>(),  // optional — The Fields that the Worker results will come back with.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Worker>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [WorkerConfigurationResponse](WorkerConfigurationResponse.md)
- [VersionInfo](VersionInfo.md)
- [Parameter](Parameter.md) — used in `Parameters`
- [ResultField](ResultField.md) — used in `ResultFields`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

