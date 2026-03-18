# Finbourne.Sdk.Horizon.Model.QuerySpecification

Defines the information that can be used to query a set of data.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Limit** | **int?** | Optional | The maximum number of results to be returned in a \&quot;page\&quot; |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new QuerySpecification(
    limit: 0  // optional — The maximum number of results to be returned in a \&quot;page\&quot;
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QuerySpecification>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

