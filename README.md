# k8s-jmc-sample

It is a Java mission control operation confirmation application of Java application that runs on kuberntes.
You can check the following actions by enabling Java Flight Recoreder.

 - Memory dump information on occurrence of Out Of Memory


### Build

`gcp.roject.name` :  specify the project ID to push to google container registry.

```
mvn -Dgcp.project.name=sample-project compile jib:build
```

### Deploy

1. Please change {change-it-me} of image of 020_deployments.yaml.

2. kubectl apply .<br>

```
spring-boot-sample>kubectl apply -f kubernetes
configmap "spring-boot-config" created
deployment "spring-boot-sample" created
service "spring-boot-sample" created
spring-boot-sample>
```
