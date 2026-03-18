# Finbourne.Sdk.Lusid.Model.ResourceRecord

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DeploymentScope** | **string** | Required | The scope of the deployment this record is part of. |
| **DeploymentCode** | **string** | Required | The code of the deployment this record is part of. |
| **ResourceId** | **string** | Required | The unique identifier of the resource associated with this record. |
| **Format** | **string** | Required | A semver format identifier for the resource record. |
| **ResourceType** | **string** | Required | The type of resource associated with this record. |
| **ResourceState** | **Object** | Required | The state of the resource associated with this record. |
| **Dependencies** | **List&lt;string&gt;** | Required | A collection of resource identifiers that this resource depends on. |
| **TrackingState** | **Object** | Optional | The tracking state of the resource record. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for the resource record at the requested effective and asAt datetime. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ResourceRecord(
    deploymentScope: "...",  // required — The scope of the deployment this record is part of.
    deploymentCode: "...",  // required — The code of the deployment this record is part of.
    resourceId: "...",  // required — The unique identifier of the resource associated with this record.
    format: "...",  // required — A semver format identifier for the resource record.
    resourceType: "...",  // required — The type of resource associated with this record.
    resourceState: ,  // required — The state of the resource associated with this record.
    dependencies: ,  // required — A collection of resource identifiers that this resource depends on.
    trackingState: ,  // optional — The tracking state of the resource record.
    varVersion: new ModelVersion(...),  // optional
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for the resource record at the requested effective and asAt datetime.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResourceRecord>(json);
```

- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

