# 📄 On-chain contracts

Ethereum Virtual Machine (EVM) contracts for managing the on-chain identity sub-system and identities.

## 🎬 Scenarios

* CLI program initiates transaction to create a new on-chain identity
* CLI program initiates transaction to modify or add identity info
* Any blockchain user ERC-20 tokens to on-chain public identity
* CLI program initiates transaction to send ERC-20 tokens from on-chain public identity
* CLI program initiates custom transaction from on-chain public identity

## 🎰 Functionality

* Identity creation and modification
* ERC-20 token send and receive
* Custom transaction execution
* // Native currency (ETH in some cases) send and receive
* // Multi-key access controls
* // Delayed and pending access controls
* // Multi-party access control

## 🗜 Interfaces

The singleton System contract has the following interface:

```
contract System {
    constructor() { }
    mapping (address => bool) public identityMap; 
    
    function createIdentity(Identity.ValueLevel _valueLevel) 
        public returns(address) { }
    function isIdentity(address) public view returns (bool) { }
    
    event IdentityCreated(address);
    event SystemCreated(address);
}
```

The identity contract which represents specific identities has the following interface:

```
contract Identity {
    constructor(address, ValueLevel) {
    address public owner;
    address public system;
    ValueLevel public valueLevel;
    mapping (uint256 => string) public propertiesMap;
    mapping(address => Key) public keyMap;
    
    function setProperties( uint256 _nameHash1, ..., uint256 _nameHash5,
        string memory _value1, ..., string memory _value5) public { }
    function addKey(address _keyAddress, uint256 _startTime, uint256 _expiryTime,
        ValueLevel _valueLevel, KeyState _state) public {}
    
    event KeyAdded(address agentKeyAddress);
    event KeyStateChanged(address keyAddress, KeyState beforeState, KeyState afterState);
    event InfoSet(uint256 nameHash, string value);
}   
```

The ValueLevel enum that is used across all object to keep track of value and security level is as follows. See the security page for more details:

{% content-ref url="../../../concepts/security.md" %}
[security.md](../../../concepts/security.md)
{% endcontent-ref %}

```
enum ValueLevel {
    Unspecified,
    None,
    VeryLow,
    Low,
    MediumLow,
    Medium,
    MediumHigh,
    High,
    VeryHigh,
    ExtremelyHigh
}
```

Key is represented as below:

```
struct Key {
        address keyAddress;
        uint256 startTime;
        uint256 expiryTime;
        ValueLevel valueLevel;
        KeyState state;
    }
```
