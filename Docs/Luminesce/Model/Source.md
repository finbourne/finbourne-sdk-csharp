# Finbourne.Sdk.Luminesce.Model.Source

Information leading to choosing the provider
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Location** | **string** | Optional | The source location.  Start of a provider name, &#x60;Drive&#x60;, &#x60;LocalFs&#x60;, &#x60;AwsS3&#x60; etc. |
| **Type** | **SourceType** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new Source(
    location: "...",  // optional — The source location.  Start of a provider name, &#x60;Drive&#x60;, &#x60;LocalFs&#x60;, &#x60;AwsS3&#x60; etc.
    type:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Source>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

