This repository contains a simple project to reproduce the issue reported in [DROOLS-7261].

Steps to reproduce:

```shell
cd drools-project
mvn clean verify
```

The build will fail with the following error:

```
[ERROR] Failed to execute goal org.kie:kie-maven-plugin:8.37.0.Final:build (default-build) on project drools-project: Execution default-build of goal org.kie:kie-maven-plugin:8.37.0.Final:build failed: Unable to create KieModule, Errors Existed: [Message [id=1, level=ERROR, path=src/main/java/drools/project/Measurement.java, line=28, column=783
[ERROR]    text=The constructor Measurement(String, String) is undefined]]
```

If the `drools-model-compiler` dependency is removed from the `drools-project` pom.xml, the build will succeed. So, the
issues appears to only affect executable models.

[DROOLS-7261]: https://issues.redhat.com/browse/DROOLS-7261
