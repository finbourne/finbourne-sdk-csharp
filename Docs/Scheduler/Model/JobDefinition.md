# Finbourne.Sdk.Scheduler.Model.JobDefinition

Definition of a job
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **JobId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Name** | **string** | Optional | Name of the job |
| **Author** | **string** | Optional | Author of the job |
| **DateCreated** | **DateTimeOffset** | Optional | Date when job was created |
| **Description** | **string** | Optional | Description of this job |
| **DockerImage** | **string** | Optional | Information about the docker image in the format “image_source/image_name:image_tag” |
| **Ttl** | **int** | Optional | Time To Live of the job run in seconds Defaults to 5 minutes(300) |
| **MinCpu** | **string** | Optional | Specifies  minimum number of CPUs to be allocated for the job Default to 2 |
| **MaxCpu** | **string** | Optional | Specifies  maximum number of CPUs to be allocated for the job |
| **MinMemory** | **string** | Optional | Specifies the minimum amount of memory (in GiB) to be allocated for the job |
| **MaxMemory** | **string** | Optional | Specifies the maximum amount of memory (in GiB) to be allocated for the job |
| **ArgumentDefinitions** | [Dictionary&lt;string, ArgumentDefinition&gt;](ArgumentDefinition.md) | Optional | All arguments for this job to run |
| **CommandLineArgumentSeparator** | **string** | Optional | Value to separate command line arguments e.g : If a job has a command line argument named &#39;folder&#39; and the runtime value is &#39;s3://path&#39; then this would be supplied to the command as &#39;folder{separatorValue}s3://path&#39; Default to a space |
| **RequiredResources** | [RequiredResources](RequiredResources.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new JobDefinition(
    jobId: new ResourceId(...),  // required
    name: "...",  // optional — Name of the job
    author: "...",  // optional — Author of the job
    dateCreated: DateTimeOffset.Now,  // optional — Date when job was created
    description: "...",  // optional — Description of this job
    dockerImage: "...",  // optional — Information about the docker image in the format “image_source/image_name:image_tag”
    ttl: 0,  // optional — Time To Live of the job run in seconds Defaults to 5 minutes(300)
    minCpu: "...",  // optional — Specifies  minimum number of CPUs to be allocated for the job Default to 2
    maxCpu: "...",  // optional — Specifies  maximum number of CPUs to be allocated for the job
    minMemory: "...",  // optional — Specifies the minimum amount of memory (in GiB) to be allocated for the job
    maxMemory: "...",  // optional — Specifies the maximum amount of memory (in GiB) to be allocated for the job
    argumentDefinitions: new ArgumentDefinition(...),  // optional — All arguments for this job to run
    commandLineArgumentSeparator: "...",  // optional — Value to separate command line arguments e.g : If a job has a command line argument named &#39;folder&#39; and the runtime value is &#39;s3://path&#39; then this would be supplied to the command as &#39;folder{separatorValue}s3://path&#39; Default to a space
    requiredResources: new RequiredResources(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<JobDefinition>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ArgumentDefinition](ArgumentDefinition.md) — used in `ArgumentDefinitions`
- [RequiredResources](RequiredResources.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

