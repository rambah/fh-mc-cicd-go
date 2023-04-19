[![Build Status](https://app.travis-ci.com/rambah/fh-mc-cicd-go.svg?branch=main)](https://app.travis-ci.com/rambah/fh-mc-cicd-go)

# MC

Ramin Bahadoorifar
Github Link: [https://github.com/rambah/fh-mc-cicd-go](https://github.com/rambah/fh-mc-cicd-go)

## Travis CI Integration

My Travis configuration is different from the assignment description, since it didn't work for me :/

```yml
language: go
go:
  - 1.20.3
services:
  - postgresql
  
addons:
  sonarcloud:
    organization: "rambah"

env:
  - APP_DB_USERNAME=postgres APP_DB_NAME=postgres

script:
  - sonar-scanner
  # Build go
  - go build -v ./...
  # Test the code
  - go test -v ./...
```

And in TravisCI I set the secret env variables for the database password and SonarCloud:
![secrets](./docs/imgs/secrets.png)

Travis SignUp:
![travis](./docs/imgs/travis.png)

Travis Builds:
![travis2](./docs/imgs/travis2.png)

SonarCloud SignUp:
![sonarcloud](./docs/imgs/sonarcloud.png)

SonarCloud Analysis
![sonarcloud2](./docs/imgs/sonarcloud2.png)

Disable Automatic Analysis and implement Travis Configuration, to analyze code on push.
![sonarcloudtravis](./docs/imgs/sonarcloudtravis.png)
