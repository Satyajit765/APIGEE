# :label: How To Add Addition header in a request using Assign Mesaage :high_brightness:

- Use this Condition to invoke the below Assign Meassage.
```xml
<Condition>(request.header.IM-SiteCode is null) or (request.header.IM-SiteCode = "")</Condition>
```

---

- Use this Assign Message.
```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<AssignMessage async="false" continueOnError="false" enabled="true" name="AM-AssignSiteCode">
    <DisplayName>AM-AssignSiteCode</DisplayName>
    <Properties/>
    <Set>
        <Headers>
            <Header name="IM-SiteCode">US</Header>
        </Headers>
    </Set>
    <IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
    <AssignTo createNew="false" transport="http" type="request"/>
</AssignMessage>
```
