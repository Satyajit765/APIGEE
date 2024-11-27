# :label: Block OPTION Call :high_brightness:

- Use this Condition and Below RaiseFault to block OPTION Call at Apigee End.
```xml
<Condition>request.verb == "OPTIONS"</Condition>
```

---

- Use thsi RaiseFault.
```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<RaiseFault continueOnError="false" enabled="true" name="Common-option">
    <DisplayName>Common-option</DisplayName>
    <Properties/>
    <FaultResponse>
        <Set>
            <Headers>
                <Header name="Access-Control-Allow-Origin">{request.header.Origin}</Header>
                <Header name="Access-Control-Allow-Headers">access-control-allow-origin,authorization,content-type,correlationid,countrycode,im-acceptlanguage,im-correlationid,im-countrycode,im-environment,im-microfrontendid,im-senderid,im-sitecode,podiosubvendorid,im-userid,isocountrycode, *</Header>
                <Header name="Access-Control-Allow-Methods">GET, HEAD, POST, PUT, DELETE, OPTIONS, PATCH, COPY, LINK, UNLINK ,PURGE, VIEW</Header>
                <Header name="Access-Control-Allow-Credentials">true</Header>
                <Header name="Access-Control-Max-Age">1800</Header>
                <Header name="Vary">Origin</Header>
                <Header name="Accept-Encoding">gzip, deflate, br</Header>
                <Header name="Content-Type">text/html,application/json</Header>
            </Headers>
            <StatusCode>204</StatusCode>
            <ReasonPhrase>OK</ReasonPhrase>
        </Set>
    </FaultResponse>
    <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
</RaiseFault>
```
