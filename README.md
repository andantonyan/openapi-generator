# Open Api Generator

## Running generator

```shell
npm start
```

## Adding new client

* add new configuration into [openapitools.json](openapitools.json) file

    ```json
    {
      "generators": {
        "example": {
          "generatorName": "java",
          "output": "#{cwd}/clients/example",
          "inputSpec": "https://example.com/swagger.json",
          "glob": "examples/v2.0/{json,yaml}/*.{json,yaml}",
          "library": "webclient",
          "groupId": "com.andantonyan",
          "artifactId": "example",
          "artifactVersion": "0.0.1-SNAPSHOT",
          "apiPackage": "com.andantonyan.client.example.api",
          "modelPackage": "com.andantonyan.client.example.model",
          "invokerPackage": "com.andantonyan.client.example",
          "skipValidateSpec": true,
          "globalProperty": {
            "apiTests": false,
            "modelTests": false,
          },
          "additionalProperties": {
            "implicitHeaders": true
          }
        }
      }
    }
    ```
* run generator
    ```shell
    npm start
    ```
* update `clients/example/.openapi-generator-ignore` file and delete unnecessary files
  ```ignorelang
  .travis.yml
  *.gradle
  build.sbt
  git_push.sh
  gradle.properties
  gradlew
  gradlew.bat
  gradle/**
  api/**
  .github/**
  src/main/AndroidManifest.xml
  ```
