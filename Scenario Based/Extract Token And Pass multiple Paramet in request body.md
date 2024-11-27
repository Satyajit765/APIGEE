# :label: Extract the bearer token and then Add addition parameter in the request body form-urlencoded :high_brightness:

- Store the credential in the KVM.
```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<KeyValueMapOperations continueOnError="false" enabled="true" name="KVM-Operations" mapIdentifier="CloudConnectCountryWise">
    <DisplayName>KVM-Operations</DisplayName>
    <Properties/>
    <ExclusiveCache>false</ExclusiveCache>
    <ExpiryTimeInSecs>300</ExpiryTimeInSecs>
    <Get assignTo="grant_type">
        <Key>
            <Parameter>grant_type</Parameter>
        </Key>
    </Get>
    <Get assignTo="client_secret">
        <Key>
            <Parameter ref="request.header.IM-SiteCode"/>
        </Key>
    </Get>
    <Get assignTo="client_id">
        <Key>
            <Parameter>client_id</Parameter>
        </Key>
    </Get>
    <Scope>environment</Scope>
</KeyValueMapOperations>
```

---

- Use this below Java Script to extract the token and assign it in request body.
```javascript
var auth = context.getVariable('request.header.Authorization');
var token = auth.substring(auth.indexOf(' ') + 1);
context.setVariable("bearerToken1",token);
var gType = context.getVariable('grant_type');
var cId = context.getVariable('client_id');
var cSecret = context.getVariable('client_secret');
var rbody = "grant_type="+ gType +"&client_secret="+ cSecret +"&client_id="+ cId +"&subject_token=" + token;
context.setVariable("request.content",rbody);
```

---

- Assign it in Header Form URL.
```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<AssignMessage async="false" continueOnError="false" enabled="true" name="AssignVerb">
    <DisplayName>AssignVerb</DisplayName>
    <Properties/>
    <Set>
        <Verb>POST</Verb>
        <Headers>
            <Header name="Content-Type">application/x-www-form-urlencoded</Header>
        </Headers>
    </Set>
    <IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
    <AssignTo createNew="false" transport="http" type="request"/>
</AssignMessage>
```


