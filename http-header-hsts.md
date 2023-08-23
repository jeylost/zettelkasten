#security #http #header

# Strict-Transport-Security
[[http-header|HTTP Header]]  inform browser that this site is intended to be used under https

- Browsers will ignore this header till the moment the site will be successfully reached under https at least once
- Browsers will remember expiration time and will keep using https until it will be expired(`max-age=0` can be used to reset)
- Each new response with this header will exchange expiration time for a new one
- recommended expiration time is 2 year(63072000)
- preload - Chrome, Firefox and others browsers will add the site to their list and clients will get this settings even before making the first request to your website

```
Strict-Transport-Security: max-age=63072000; includeSubDomains; preload
```

[MDN documentation](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Strict-Transport-Security)
To check your website configurations, visit https://hstspreload.org
