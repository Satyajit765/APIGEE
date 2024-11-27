# :label: Validate Apigee OAuth2 :high_brightness:

- You need to add OAuthV2 Policy into that proxy where you want to validate OAuth plus make sure the Proxy is added to that product as well.

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<OAuthV2 continueOnError="false" enabled="true" name="OAuth-v20-1">
    <DisplayName>OAuth v2.0-1</DisplayName>
    <Properties/>
    <Attributes/>
    <ExternalAuthorization>false</ExternalAuthorization>
    <Operation>VerifyAccessToken</Operation>
    <SupportedGrantTypes/>
    <GenerateResponse enabled="true"/>
    <Tokens/>
    <RFCCompliantRequestResponse>true</RFCCompliantRequestResponse>
</OAuthV2>
```