# :label::bookmark: Condition to Increase Timeout :high_brightness:
---

- Add this below the Target URL.
```xml
<HTTPTargetConnection>
        <URL>https://MockAPI.com</URL>
        <Properties>
            <Property name="io.timeout.millis">300000</Property>
        </Properties>
</HTTPTargetConnection>
```

---
---

# :label::bookmark: Condition to Increase BufferSize :high_brightness:
---

- Add this below the BasePath of the proxy and the Target URL as well.
```xml
<HTTPTargetConnection>
        <URL>https://MockAPI.com</URL>
        <Properties>
            <Property name="response.streaming.enabled">true</Property>
            <Property name="request.streaming.enabled">true</Property>
        </Properties>
</HTTPTargetConnection>
```