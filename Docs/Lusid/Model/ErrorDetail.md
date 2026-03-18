# Finbourne.Sdk.Lusid.Model.ErrorDetail

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Optional | The id of the failed item that this error relates to. |
| **Type** | **string** | Optional | The type of failure that occurred. |
| **Detail** | **string** | Optional | Description of the failure that occurred. |
| **ErrorDetails** | **List&lt;Dictionary&lt;string, string&gt;&gt;** | Optional | Information about the particular instance of the failure (supplied information depends on the type of failure). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ErrorDetail(
    id: "...",  // optional — The id of the failed item that this error relates to.
    type: "...",  // optional — The type of failure that occurred.
    detail: "...",  // optional — Description of the failure that occurred.
    errorDetails:   // optional — Information about the particular instance of the failure (supplied information depends on the type of failure).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ErrorDetail>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

