# UID library

General purpose libraries, containing key UID functionality, for all layers of the stack, are written for each technology stack such as .NET Core 6, to be used in all modalities including on-device app and back end services.

Modalities to be supported:

* Native device app
* Native desktop CLI app
* Back-end app service
* Back-end identity operator service
* Storage modes
  * File
  * Database (MongoDB as default or other)

## Layers and sub-components

* **Storage** - The layer responsible for storing identity box information, as well as performing signing and verification operations on individual information fragments. Each instance of a storage unit is logically referred to as an "id-box".
  * **Repository** - A sub-layer of storage, this sub-component is responsible for storage and access of tamper proof Content Addressable Storage (CAS) similar to Git, but with a few additional required features. Each repository instance is logically referred to as a "box"
* **Runtime** - The layer containing the in-memory object model that exposes higher level APIs for accessing and interacting with the stored identity box. The objects in this layer can be bound to XAML views as models, and these objects can also be accessed by communication protocols and other coordination mechanisms.
* **Communication** - This layer is built on top of libp2p and contains the sub-components for each protocol communication protocol including Sync, Interchange, Replication and Beacon.
* **Interactive** - This layer deals with secure interactions with users as well as machine agents for the purposes of signing and securing interactions. It performs most if not all of the signing activity at the highest level.
* **UI controls** (Out of scope) - Common XAML UI components to be re-used by all apps built on top of the platform. These include controls such as identity view/update, identity selection, identity information view/update, app connection agreement, contact view/update, privacy agreement, etc.

## Scenarios

* Developer programmatically creates an identity-box
* Developer programmatically opens an identity box



## Interfaces

Functionality of the library related to managing and operating an IdBox instance are encapsulated by the IdBoxService object API. The hierarchy of IdBoxService and nested objects are as follows:

* IdBoxService
  * Storage: IdBoxStorage
    * FileRepository
  * Communication: CommunicationService
    * LibP2pSwarm
  * // Runtime: IdBoxRuntime
  * // Interaction: IdBoxInteractionService

The interface to service objects are as follows

```
public class IdBoxService
{
    public IdBoxService(string path) {}
    public IdBoxStorage Storage { get; }
    // public CommunicationService Communication {}
}
```

Sample JSON data for `IdBoxStorage` as `id-box.json`:

```
{
    "primary-identity" : "0x45dD963323A801333876785E20c7EF19FF120208"
}
```

Sample JSON data for `IdentityStorage` as `identities/{identifier}/identity.json`:

```
{
    "identifier" : "0x45dD963323A801333876785E20c7EF19FF120208",
    "level" : "1",
    "keys" : [ {
        "identifier" : "0x45dD963323A801333876785E20c7EF19FF120208",
        "level" : "1",
        "status" : "active",
        "created" : "1597342829",
        "publicKey" : "0x0447c621934de7162d908142a12797b9557050b3ce5bb029eca146f39fbcd60de250ebff2713c5ae046e3996a14e8a81d8d86089250b9aab7878f6d21f737b745d" }, ],
    // "controls" : [ {
    //     "type" : "root",
    //     "keys" : "0x45dD963323A801333876785E20c7EF19FF120208" },
    //     { "type" : "operator",
    //     "keys" : "0x2C8A0CCFDb1C79e5C60c3d1576583c5C7D3A7310" }
    // ],
    // "info" : [ {
    //     "key" : "name",
    //     "value" : "Connie Connor" },
    //     { "key" : "email",
    //     "value" : "connie.connor@mail.com" },
    //     { "key" : "image",
    //     "value" : "A1B35DA7234EF234...46FABC89D0B" } ]
}
```
