# Finbourne.Sdk.Identity.Model.NetworkZoneDefinitionResponse

The Client facing representation of a NetworkZone
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Optional | The Network Zone Code |
| **Hierarchy** | **int** | Optional | Hierarchy of the Network Zone |
| **Description** | **string** | Optional | The Description of the Network Zone |
| **CreatedAt** | **DateTimeOffset** | Optional | Network Zone Creation timestamp |
| **UpdatedAt** | **DateTimeOffset** | Optional | Timestamp of the last update |
| **NetworkZoneIPs** | [List&lt;IpAddressDefinition&gt;](IpAddressDefinition.md) | Optional | Network zone IP information (IPs and CIDR ranges) |
| **Action** | **string** | Optional | Kind of action to apply when a request matches this Network Zone (Block/Allow/NoOp) |
| **ApplyRules** | [NetworkZonesApplyRules](NetworkZonesApplyRules.md) | Optional | *No description available.* |
| **CreatedBy** | **string** | Optional | User Id that created the Network Zone |
| **UpdatedBy** | **string** | Optional | User Id of the last update on the Network Zone |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new NetworkZoneDefinitionResponse(
    code: "...",  // optional — The Network Zone Code
    hierarchy: 0,  // optional — Hierarchy of the Network Zone
    description: "...",  // optional — The Description of the Network Zone
    createdAt: DateTimeOffset.Now,  // optional — Network Zone Creation timestamp
    updatedAt: DateTimeOffset.Now,  // optional — Timestamp of the last update
    networkZoneIPs: new List<IpAddressDefinition>(),  // optional — Network zone IP information (IPs and CIDR ranges)
    action: "...",  // optional — Kind of action to apply when a request matches this Network Zone (Block/Allow/NoOp)
    applyRules: new NetworkZonesApplyRules(...),  // optional
    createdBy: "...",  // optional — User Id that created the Network Zone
    updatedBy: "..."  // optional — User Id of the last update on the Network Zone
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<NetworkZoneDefinitionResponse>(json);
```

- [IpAddressDefinition](IpAddressDefinition.md) — used in `NetworkZoneIPs`
- [NetworkZonesApplyRules](NetworkZonesApplyRules.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

