# OAuth2 Authorization Server

Minimal gradle project Springboot Oauth 2 Authorization Server.

**Requirements**

* Pass as arguments application.properties properties.
* Generate new keystore (apendix).
* Rewrite all TODO's in source code.

# Run

```sh
./gradlew clean bootRun
```

# Apendix

## Java KeyStore creation

```sh
keytool -genkey -v -keystore mykeystore.keystore -alias myalias -keyalg RSA -keysize 2048 -validity 10000
keytool -v -list -keystore mykeystore.keystore -alias myalias
```

## CURL get AccessToken

```sh
curl -X POST -u myclientid:myclientsecret http://localhost:8080/oauth/token \
-H"content-type: application/x-www-form-urlencoded" \
-d"grant_type=password&username=myusername&password=mypassword" | jq .
```

## Prepare for Eclipse Java Project

```sh
./gradlew cleanEclipse eclipse
```

