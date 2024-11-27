# :label: How To send the Basic Credential to Backend using KVM:high_brightness:

- You Can use KVM To store the credential and create the mapIdentifier in The Env Configuration.

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<KeyValueMapOperations name="KVM-Operation" enabled="true" continueOnError="false" async="false" mapIdentifier="USITIMAppEAI">
    <DisplayName>KVM-Operation</DisplayName>
    <Properties/>
    <ExclusiveCache>false</ExclusiveCache>
    <ExpiryTimeInSecs>300</ExpiryTimeInSecs>
    <Get assignTo="private.Username" index="1">
        <Key>
            <Parameter>Username</Parameter>
        </Key>
    </Get>
    <Get assignTo="private.Password" index="1">
        <Key>
            <Parameter>Password</Parameter>
        </Key>
    </Get>
    <Scope>environment</Scope>
</KeyValueMapOperations>
```
---

- Then Pass the Credential to the target for that use BasicAuthentication Policy.

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<BasicAuthentication async="false" continueOnError="false" enabled="true" name="BA-Authentication">
    <DisplayName>BA-Authentication</DisplayName>
    <Operation>Encode</Operation>
    <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
    <User ref="private.Username"/>
    <Password ref="private.Password"/>
    <AssignTo createNew="true">request.header.Authorization</AssignTo>
    <Source>request.header.Authorization</Source>
</BasicAuthentication>
```