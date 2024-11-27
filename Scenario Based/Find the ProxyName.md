# :label: How To find the Proxy Name using Assign message:high_brightness:

- You Can use this Assign message to the proxy and add the Proxy Name .

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<AssignMessage async="false" continueOnError="false" enabled="true" name="AM-ProxyNameToRespHeader">
    <DisplayName>AM-ProxyNameToRespHeader</DisplayName>
    <Add>
        <Headers>
            <Header name="ProxyName">{apiproxy.name}</Header>
        </Headers>
    </Add>
    <IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
    <AssignTo createNew="false" transport="http" type="response"/>
</AssignMessage>
```
