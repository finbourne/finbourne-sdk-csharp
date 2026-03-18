# Finbourne.Sdk.Identity.Model.CreateNetworkZoneRequest

The Create Network Zone Request information
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **NetworkZoneIPs** | [List&lt;IpAddressDefinition&gt;](IpAddressDefinition.md) | Required | *No description available.* |
| **Action** | **string** | Optional | *No description available.* |
| **ApplyRules** | [NetworkZonesApplyRules](NetworkZonesApplyRules.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new CreateNetworkZoneRequest(
    code: "...",  // required
    description: "...",  // optional
    networkZoneIPs: new List<IpAddressDefinition>(),  // required
    action: "...",  // optional
    applyRules: new NetworkZonesApplyRules(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateNetworkZoneRequest>(json);
```

- [IpAddressDefinition](IpAddressDefinition.md)
- [NetworkZonesApplyRules](NetworkZonesApplyRules.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

