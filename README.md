# A Simple Java Web App (Maven + Jetty) with Containerize

## Build
```shell
mvn package
```

## Run Locally
```shell
mvn jetty:run
```
To run in a different port
```shell
mvn jetty:run -Djetty.port=<your port>
```
To test your run locally (Health Ping)
```shell
http://localhost:8080<or your port>/api/calculator/ping
```
To test your run locally (Web Service Function Call With Arithmetic operator +, -, *, /)
```shell
http://localhost:8080/api/calculator/add?x=6&y=6
http://localhost:8080/api/calculator/sub?x=10&y=2
http://localhost:8080/api/calculator/mul?x=6&y=6
http://localhost:8080/api/calculator/div?x=12&y=2
```

## Debug Locally
```shell
set MAVEN_OPTS=-Xdebug -Xrunjdwp:transport=dt_socket,server=y,address=8000,suspend=n
mvn jetty:run
```

## Containerize
1. Build a docker image using `Dockerfile`:
   ```
   docker build -t calculator .
   ```
2. Run docker image locally
   ```
   docker run --rm -p 8080:8080 calculator
   ```
3. Then you can access the web app at http://localhost:8080/api/calculator/ping in browser

