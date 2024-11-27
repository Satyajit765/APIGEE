# :label: Validate Apigee OAuth2 :high_brightness:

- You need to Need App OAuthV2 to validate and add the credential in that Product as well.

```xml
<PublishMessage continueOnError="false" enabled="true" name="Publish-Message-1">
    <DisplayName>Publish Message-1</DisplayName>
    <Source>{flow-variable-1}</Source>
    <CloudPubSub>
        <Topic>projects/{flow-variable-project-id}/topics/{flow-variable-topic-name}</Topic>
    </CloudPubSub>
    <IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
</PublishMessage>
```