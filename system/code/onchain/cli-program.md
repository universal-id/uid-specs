# 💻 CLI program

This section is incomplete ...

## 👩🏻 Users

Early adopters and developers use the CLI client to access their (or their entity's) public identities on the blockchain using advanced commands and tools. They may even self-compile the application on their device platform before running it.

{% embed url="https://map.universal.id/personas#early-adopter-earl-and-erica" %}
Early adopter persona under Personas page of the Industry map
{% endembed %}

## 🎬 Scenarios

* Early adopter creates a new on-chain public identity
* Early adopter modifies an on-chain public identity
* Early adopter sends ERC-20 tokens to on-chain public identity
* Early adopter sends ERC-20 tokens from on-chain public identity
* Early adopter executes a custom transaction from on-chain public identity
* // Early adopter adds a new device that syncs identities with original device
* // Early adopter adds new identity-key as controller of on-chain public identity
* // Early adopter transforms identity into multi-party by adding new identities and their keys.

## 🎰 Functionality

### Modes of operation

* Stateless commands - Isolated Command that have all required parameters passed in.
* Stateful commands - Commands run separately but with parameters set by previous commands.
* Interactive (stateful) commands - Commands run interactively as the user inputs them.

#### Interactive commands

Commands run interactively as the user inputs them, while other inputs and outputs are also available to the user. See example sample below where `>>` appears before interactive commands and `<<` before input prompts:

```
uid interactive
>> box open file://folder/idbox
>> onchain create-request
>> onchain info-request add --key "name" --value "Erica"
>> onchain execute-requests
Request: Create identity contract:
{ "identifer" : "0xABCD1234..",
"keys" [ { "idetifier" : "0xABCD1234..", ...} ],
"info" : { "name" : "Erica" } }
<< do you want to execute the transaction on-chain? (y/n)
<< _ 
```

### State

The state will be stored under the folder that stateful commands were run. For example if one runs the command `idbox open c:\folder` under `c:\` there will be a folder `c:\.idbox` created under which the state is saved. State is stored in a `state.json` and it looks like this:

```
{
    "path" : "c:\folder",
    "selectedIdentity" : "0xAB4245CD62348EF8237429347923469EFDACB3234",
    // "selectedConnection" : "0x9347923469EFDACB3234AB4245CD62348EF823742",
    "onChainRequest" : { "identifer" : "0xABCD1234..",
        "keys" [ { "idetifier" : "0xABCD1234..", ...} ],
        "info" : { "name" : "Erica" } }
}
```

### Dependencies

Given that the .NET Core team is using the following library for their internal and public projects, it makes sense to use the same library for our project:

{% embed url="https://github.com/dotnet/command-line-api" %}
Command Line Interface API used by the .NET Core team
{% endembed %}

## 🎭 Demo script

As mentioned in the PoC description, the following demo scripts cover the most visible features of the CLI client.

```
uid box create file://folder/idbox
uid box open file://folder/idbox
uid interactive
>> box open file://folder/idbox
>> onchain create-request
>> onchain info-request add --key "name" --value "Erica"
>> onchain execute-requests
Request: Create identity contract:
{ "identifer" : "0xABCD1234..",
"keys" [ { "idetifier" : "0xABCD1234..", ...} ],
"info" : { "name" : "Erica" } }
<< do you want to execute the transaction on-chain? (y/n)

```

## 📺 Experience

Low fidelity experience of using the CLI program:

Incomplete ...
