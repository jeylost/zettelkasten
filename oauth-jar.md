#oauth #security 
JWT-Secured Authorization Request(JAR) is a way to add [[oauth-non-repudiation|non-repudiation]] to authorization request. Merely a [[jwt]] signed by a client private key

Using JAR for authorization request [[oauth-roles#Application|client]] puts all parameters inside jwt, signs it and pass jwt inside `request` query parameter or as `request_uri`(URL from where [[oauth-roles|OAuth Server]] can fetch this jwt)

```
by request:
https://server.example.com/authorize?client_id=s6BhdRkqt3&
    request=eyJhbGciOiJSUzI1NiIsImtpZCI6ImsyYmRjIn0.ewogICAgImlzcyI6
    ICJzNkJoZFJrcXQzIiwKICAgICJhdWQiOiAiaHR0cHM6Ly9zZXJ2ZXIuZXhhbXBs
    ZS5jb20iLAogICAgInJlc3BvbnNlX3R5cGUiOiAiY29kZSBpZF90b2tlbiIsCiAg
    ICAiY2xpZW50X2lkIjogInM2QmhkUmtxdDMiLAogICAgInJlZGlyZWN0X3VyaSI6
    ICJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9jYiIsCiAgICAic2NvcGUiOiAi
    b3BlbmlkIiwKICAgICJzdGF0ZSI6ICJhZjBpZmpzbGRraiIsCiAgICAibm9uY2Ui
    OiAibi0wUzZfV3pBMk1qIiwKICAgICJtYXhfYWdlIjogODY0MDAKfQ.Nsxa_18VU
    ElVaPjqW_ToI1yrEJ67BgKb5xsuZRVqzGkfKrOIX7BCx0biSxYGmjK9KJPctH1OC
    0iQJwXu5YVY-vnW0_PLJb1C2HG-ztVzcnKZC2gE4i0vgQcpkUOCpW3SEYXnyWnKz
    uKzqSb1wAZALo5f89B_p6QA6j6JwBSRvdVsDPdulW8lKxGTbH82czCaQ50rLAg3E
    YLYaCb4ik4I1zGXE4fvim9FIMs8OCMmzwIB5S-ujFfzwFjoyuPEV4hJnoVUmXR_W
    9typPf846lGwA8h9G9oNTIuX8Ft2jfpnZdFmLg3_wr3Wa5q3a-lfbgF3S9H_8nN3
    j1i7tLR_5Nz-g
by reference:
  https://server.example.com/authorize?
    client_id=s6BhdRkqt3
    &request_uri=https%3A%2F%2Ftfp.example.org%2Frequest.jwt
    %2FGkurKxf5T0Y-mnPFCHqWOMiZi4VS138cQO_V7PZHAdM
```

[rfc 9101](https://datatracker.ietf.org/doc/html/rfc9101)