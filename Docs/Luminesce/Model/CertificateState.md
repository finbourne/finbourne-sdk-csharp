# Finbourne.Sdk.Luminesce.Model.CertificateState

Information held about the minting / revoking of a certificate. It does *not* contain the certificate itself
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Optional | The \&quot;key\&quot; to which this belongs in the dictionary, basically the CN without any version information |
| **VarVersion** | **int** | Optional | The version of this certificate |
| **CommonName** | **string** | Optional | The common Name of the Certificate |
| **Type** | **CertificateType** | Optional | *No description available.* |
| **CreationStatus** | **CertificateStatus** | Optional | *No description available.* |
| **RevocationStatus** | **CertificateStatus** | Optional | *No description available.* |
| **ValidityStart** | **DateTimeOffset?** | Optional | The earliest point at which a certificate can be used |
| **ValidityEnd** | **DateTimeOffset?** | Optional | The latest point at which a certificate can be used |
| **RevokedAt** | **DateTimeOffset?** | Optional | The point at which this was revoked, if any |
| **RevokedBy** | **string** | Optional | The user which revoked this, if any |
| **CreatedAt** | **DateTimeOffset?** | Optional | The point at which this was created |
| **PermissionsSetAt** | **DateTimeOffset?** | Optional | The point at which permissions were adjusted by the system |
| **CreatedBy** | **string** | Optional | The user which created this |
| **SerialNumber** | **string** | Optional | The Vault-issued serial number of the certificate, if any - used for revocation |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | The location within Configuration Store that this is saved to |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new CertificateState(
    key: "...",  // optional — The \&quot;key\&quot; to which this belongs in the dictionary, basically the CN without any version information
    varVersion: 0,  // optional — The version of this certificate
    commonName: "...",  // optional — The common Name of the Certificate
    type: ,  // optional
    creationStatus: ,  // optional
    revocationStatus: ,  // optional
    validityStart: DateTimeOffset.Now,  // optional — The earliest point at which a certificate can be used
    validityEnd: DateTimeOffset.Now,  // optional — The latest point at which a certificate can be used
    revokedAt: DateTimeOffset.Now,  // optional — The point at which this was revoked, if any
    revokedBy: "...",  // optional — The user which revoked this, if any
    createdAt: DateTimeOffset.Now,  // optional — The point at which this was created
    permissionsSetAt: DateTimeOffset.Now,  // optional — The point at which permissions were adjusted by the system
    createdBy: "...",  // optional — The user which created this
    serialNumber: "...",  // optional — The Vault-issued serial number of the certificate, if any - used for revocation
    links: new List<Link>()  // optional — The location within Configuration Store that this is saved to
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CertificateState>(json);
```

- [Link](Link.md) — used in `Links`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

