# Storage

This is the top encompassing layer for storage which subsumes/contains the repository layer. The interface to this layer has logic specific to an identity box (IdBox) such as with objects like identity, connection etc. The layer is responsible for serializing/deserializing against the repository (box) layer, as well as a set of business logic specific to the operation of IdBox objects.

## Scenarios

* Developer programmatically creates and identity box (IdBox).
* Developer programmatically creates a seed identity as the first primary identity.
  * Developer programmatically creates additional seed identities.
* Developer programmatically updates an existing identity with added key information
  * Developer programmatically updates an existing identity with identity info.
* Developer programmatically reads identity information given an identifier
* \-------- Security scenarios (out of scope for first pass) -----------------
* Developer programmatically verifies cryptographic provenance of identity
* Developer programmatically records signature information of a given change to an identity
* Developer programmatically verifies signature of a given change to an identity

## Interfaces

The hierarchy of storage objects are as follows:

* IdBoxStorage
  * IdentityStorage
    * KeyStorage

The interface to storage objects are as follows

```
public class IdBoxStorage : IJsonSerializable<IdBoxStorage>
{
    public IdBoxStorage(string path) {}
    public FileRepository Repository { get; }
    public void InitializeStorage() {}
    public string? PrimaryIdentity { get; set; }
    public Dictionary<string, IdentityStorage> Identities { get; } 
    public IdentityStorage SaveIdentity(IdentityStorage identityStorage) {}
    public IdentityStorage ReadIdentity(string identifier) {}
    public void FromJson(JObject documentJson) {}
    public JObject ToJson() {}
}

public class IdentityStorage : IJsonSerializable<IdentityStorage>
{
    public string Identifier { get; set; }
    public ValueLevel Level { get; set; }
    public KeyStorage[] Keys { get; set; }
    public void FromJson(JObject documentJson) {}
    public JObject ToJson() {}
}

public class KeyStorage // : IJsonSerializable<KeyStorage> Key as part of identity
{
    public string Identifier { get; set; }
    public ValueLevel Level { get; set; }
    public long Created { get; set; }
    public string PublicKey { get; set; }
    // public void FromJson(JObject documentJson) {} Key as part of identity
    // public JObject ToJson() {} Key as part of identity
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
