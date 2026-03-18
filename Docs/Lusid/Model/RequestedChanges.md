# Finbourne.Sdk.Lusid.Model.RequestedChanges

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AttributeCount** | **int** | Optional | Number of attributes staged change applies to |
| **AttributeNames** | **List&lt;string&gt;** | Optional | Names of the attributes the staged change applies to. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RequestedChanges(
    attributeCount: 0,  // optional — Number of attributes staged change applies to
    attributeNames:   // optional — Names of the attributes the staged change applies to.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RequestedChanges>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

