# Finbourne.Sdk.Lusid.Model.BucketSetDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | *No description available.* |
| **DisplayName** | **string** | Required | *No description available.* |
| **NavTypes** | **List&lt;string&gt;** | Optional | *No description available.* |
| **Unitised** | **bool** | Required | *No description available.* |
| **Buckets** | [List&lt;BucketDefinition&gt;](BucketDefinition.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketSetDefinition(
    code: "...",  // required
    displayName: "...",  // required
    navTypes: ,  // optional
    unitised: true,  // required
    buckets: new List<BucketDefinition>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketSetDefinition>(json);
```

- [BucketDefinition](BucketDefinition.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

