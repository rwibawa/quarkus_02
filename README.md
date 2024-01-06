# quarkus_02
Learn quarkus
* [Maven tooling](https://quarkus.io/guides/maven-tooling)

## 1. Setup
```shell
$ export JAVA_HOME="C:\Users\Ryan\.jdks\graalvm-ce-17"
$ export GRAALVM_HOME=$JAVA_HOME
$ $M2_HOME="C:\Users\Ryan\Documents\workspaces\workspace_java\apache-maven-3.9.6"
$ export PATH=$PATH:$$JAVA_HOME/bin:$M2_HOME/bin

$ java -version
openjdk version "17.0.8" 2023-07-18
OpenJDK Runtime Environment GraalVM CE 22.3.3 (build 17.0.8+7-jvmci-22.3-b22)
OpenJDK 64-Bit Server VM GraalVM CE 22.3.3 (build 17.0.8+7-jvmci-22.3-b22, mixed mode, sharing)

$ mvn --version
Apache Maven 3.9.6 (bc0240f3c744dd6b6ec2920b3cd08dcc295161ae)
Maven home: C:\Users\Ryan\Documents\workspaces\workspace_java\apache-maven-3.9.6
Java version: 17.0.8, vendor: GraalVM Community, runtime: C:\Users\Ryan\.jdks\graalvm-ce-17
Default locale: en_US, platform encoding: Cp1252
OS name: "windows 10", version: "10.0", arch: "amd64", family: "windows"


$ mvn io.quarkus.platform:quarkus-maven-plugin:3.6.4:create -DprojectGroupId=com.navisow.quarkus -DprojectArtifactId=quarkus_01

```

## Quarkus Reference:
This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:
```shell script
./mvnw compile quarkus:dev
```

> **_NOTE:_**  Quarkus now ships with a Dev UI, which is available in dev mode only at http://localhost:8080/q/dev/.

## Packaging and running the application

The application can be packaged using:
```shell script
./mvnw package
```
It produces the `quarkus-run.jar` file in the `target/quarkus-app/` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `target/quarkus-app/lib/` directory.

The application is now runnable using `java -jar target/quarkus-app/quarkus-run.jar`.

If you want to build an _über-jar_, execute the following command:
```shell script
./mvnw package -Dquarkus.package.type=uber-jar
```

The application, packaged as an _über-jar_, is now runnable using `java -jar target/*-runner.jar`.

## Creating a native executable

You can create a native executable using: 
```shell script
./mvnw package -Dnative
```

Or, if you don't have GraalVM installed, you can run the native executable build in a container using: 
```shell script
./mvnw package -Dnative -Dquarkus.native.container-build=true
```

You can then execute your native executable with: `./target/quarkus_02-1.0.0-SNAPSHOT-runner`

If you want to learn more about building native executables, please consult https://quarkus.io/guides/maven-tooling.

## Provided Code

### RESTEasy Reactive

Easily start your Reactive RESTful Web Services

[Related guide section...](https://quarkus.io/guides/getting-started-reactive#reactive-jax-rs-resources)
