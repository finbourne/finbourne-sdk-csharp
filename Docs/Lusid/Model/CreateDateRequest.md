# Finbourne.Sdk.Lusid.Model.CreateDateRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DateId** | **string** | Required | *No description available.* |
| **FromUtc** | **DateTimeOffset** | Required | *No description available.* |
| **ToUtc** | **DateTimeOffset** | Required | *No description available.* |
| **VarTimeZone** | **string** | Required | *No description available.* |
| **Description** | **string** | Required | *No description available.* |
| **Type** | **string** | Optional | *No description available.* |
| **Attributes** | [DateAttributes](DateAttributes.md) | Optional | *No description available.* |
| **SourceData** | **Dictionary&lt;string, string&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateDateRequest(
    dateId: "...",  // required
    fromUtc: DateTimeOffset.Now,  // required
    toUtc: DateTimeOffset.Now,  // required
    varTimeZone: "...",  // required
    description: "...",  // required
    type: "...",  // optional
    attributes: new DateAttributes(...),  // optional
    sourceData:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateDateRequest>(json);
```

- [DateAttributes](DateAttributes.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

