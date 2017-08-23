# sample-oauth2-spring-gson

## Get token

Run the app:

```bash
./gradlew bootRun
```

Get the token with:

```bash
curl -q -u secretOSClient:secret -X POST http://localhost:8080/oauth/token -d "username=username&password=password&grant_type=password"
```

You will see something like:
```bash
{"access_token":"af37b08e-10ca-42c0-b75b-43347ff9ba07","token_type":"bearer","expires_in":43199,"scope":"read write"}%
```

## Change the default parser to gson and try again

Open the file **src/main/resources/application.properties** and set spring.http.converters.preferred-json-mapper=gson. Save and close.
Then run the app again with:

```bash
./gradlew bootRun
```

Try to get the token an you will see that the response is empty.. why?