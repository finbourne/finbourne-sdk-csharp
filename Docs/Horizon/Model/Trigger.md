# Finbourne.Sdk.Horizon.Model.Trigger

Response defining a trigger for an instance.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | *No description available.* |
| **CronExpression** | **string** | Required | *No description available.* |
| **VarTimeZone** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new Trigger(
    type: "...",  // required
    cronExpression: "...",  // required
    varTimeZone: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Trigger>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

