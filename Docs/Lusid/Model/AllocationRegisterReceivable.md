# Finbourne.Sdk.Lusid.Model.AllocationRegisterReceivable

What one register is owed on a booked capital call, across every record called on its lines.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Portfolio** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Called** | **decimal** | Optional | What was called on the register&#39;s lines. |
| **Received** | **decimal** | Optional | What has settled the register&#39;s lines so far. |
| **Outstanding** | **decimal** | Optional | What the register is still owed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationRegisterReceivable(
    portfolio: new ResourceId(...),  // optional
    called: 0.0d,  // optional — What was called on the register&#39;s lines.
    received: 0.0d,  // optional — What has settled the register&#39;s lines so far.
    outstanding: 0.0d  // optional — What the register is still owed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationRegisterReceivable>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

