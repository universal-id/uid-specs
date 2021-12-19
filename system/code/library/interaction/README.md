# 🗝 Interaction

This layer contains the functionality for the user and machine agents to interact securely with the system. This layer deals with storage and access of private keys as well as private key signing operations. The layer also deals with local or remote interaction with users in a manner that preserves security.

This section is incomplete ... Will complete soon.

## 🎬 Scenarios

* Developer programmatically invokes a key creation and storage process.
* Developer programmatically invokes a local interactive user signing operation.
* Developer programmatically invokes a machine agent signing operation.
* Developer programmatically invokes an app redirect process for user signing.
* Developer programmatically initiates an offline code-based user signing operation.
* Developer programmatically completes an offline code-based user signing operation.

## 🎰 Functionality

* Key creation and storage
* Key access and signing
* Native app redirect
* Remote interaction
* Offline interaction

## 🗜 Interfaces

The interaction service object will have the following interface:

```
public class InteractionService
{
    public InteractionService(string path) {}
    public string Path { get; set; }
    public void Init() {}
    public EthKey CreateAndStoreNewKey() {}
    public byte[] SignData(string keyIdentifier, byte[] data) {}
} 
```

The interfaces for the beacon protocol are:

```
public class BeaconProtocol : IPeerProtocol
{
```
