# Finbourne.Sdk.Scheduler.Model.RequiredResources

Information related to a jobs required access to resources
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LusidApis** | **List&lt;string&gt;** | Optional | List of LUSID APIs the job needs access to |
| **LusidFileSystem** | **List&lt;string&gt;** | Optional | List of S3 bucket or folder names that the job can access |
| **ExternalCalls** | **List&lt;string&gt;** | Optional | External URLs that the job can call |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new RequiredResources(
    lusidApis: ,  // optional — List of LUSID APIs the job needs access to
    lusidFileSystem: ,  // optional — List of S3 bucket or folder names that the job can access
    externalCalls:   // optional — External URLs that the job can call
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RequiredResources>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

