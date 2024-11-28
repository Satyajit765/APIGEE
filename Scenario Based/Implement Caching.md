# :label: How to implement Caching in a proxy :high_brightness:


- Use ResponseCache policy to do the caching in Apigee and and add the policy in  preflow and postflow of the traget URL.
```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<ResponseCache async="false" continueOnError="false" enabled="true" name="ResponseCacheDynamicContent">
    <DisplayName>ResponseCacheDynamicContent</DisplayName>
    <Properties/>
    <CacheKey>
        <Prefix/>
        <KeyFragment ref="request.uri" type="string"/>
        <KeyFragment ref="request.header.IM-AcceptLanguage"/>
        <KeyFragment ref="request.header.IM-MicroFrontendID"/>
        <KeyFragment ref="request.header.IM-Environment"/>
        <KeyFragment ref="request.header.IM-SenderID"/>
        <KeyFragment ref="request.header.IM-SiteCode"/>
        <KeyFragment ref="request.header.isocountrycode"/>
        <KeyFragment ref="request.header.IM-ResellerID"/>
    </CacheKey>
    <Scope>Exclusive</Scope>
    <ExpirySettings>
        <ExpiryDate/>
        <TimeOfDay/>
    </ExpirySettings>
    <CacheResource>CMS-ExpAPIDynamicContent</CacheResource>
    <SkipCacheLookup/>
    <SkipCachePopulation/>
</ResponseCache>
```
