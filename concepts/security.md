# Security

## Security levels

Designating levels of value to identities, keys and other security artifacts is useful as it can aid in measuring security levels as well as automating a range of security operations.

Value levels or security levels are used to approximately quantify the order of magnitude of potential harm caused by unexpected negative outcomes. Such harm can occur due a combination of, but not limited to: loss of keys, loss of funds, identity fraud, attacks on the integrity of the system, attack on the cryptographic subsystems, etc.

![Security levels and visual design][security-levels]

[security-levels]: security/security-levels@500w.png

|Security levels and visual design|

|Level|Name|Formula|Approximate value (order of magnitude)|
|-----|----|-------|--------------------------------------|
|-2|None (Extremely low)|100 ^ -2|$0.0001
|-1|Very low|100 ^ -1|$0.01
|0|Low|100 ^ 0|$1
|1|Medium low|100 ^ 1|$100
|2|Medium|100 ^ 2|$10K
|3|Medium high|100 ^ 3|$1M
|4|High|100 ^ 4|$100M
|5|Very high|100 ^ 5|$10B
|6|Extremely high|100 ^ 6|$1T
|7|Ultimately high|100 ^ 7|$100T

As such, increasing the level of security may require steps to mitigate against the risk of well known negative outcomes. Enumerating the actual harms possible due to these risks (negative outcomes) can be a specific and useful guide to users when asking them to perform specific actions, which makes for more usable experiences.
