# Finbourne.Sdk.Lusid.Model.UpsertResourceRecordRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DeploymentScope** | **string** | Required | *No description available.* |
| **DeploymentCode** | **string** | Required | *No description available.* |
| **ResourceId** | **string** | Required | *No description available.* |
| **Format** | **string** | Required | *No description available.* |
| **ResourceType** | **string** | Required | *No description available.* |
| **ResourceState** | **Object** | Required | *No description available.* |
| **Dependencies** | **List&lt;string&gt;** | Required | *No description available.* |
| **TrackingState** | **Object** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertResourceRecordRequest(
    deploymentScope: "...",  // required
    deploymentCode: "...",  // required
    resourceId: "...",  // required
    format: "...",  // required
    resourceType: "...",  // required
    resourceState: ,  // required
    dependencies: ,  // required
    trackingState:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertResourceRecordRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

