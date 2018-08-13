# k8s-jmc-sample

It is a Java mission control operation confirmation application of Java application that runs on kuberntes.
You can check the following actions by enabling Java Flight Recoreder.

 - Memory dump information on occurrence of Out Of Memory


### ビルド
下記コマンドを実行するだけで、Google Container Registryにイメージが登録されます。
`sample-project` は、GCPプロジェクト名を指定してください。

```
mvn -Dgcp.project.name=sample-project compile jib:build
```

### 配備
下記コマンドを実行し、kubernetesに配備を行います。<br>
deployments.xmlのimage部分のGCPプロジェクト名は適宜変更を行ってください。
そして、 `gcloud container clusters get-credentials ～ ` コマンドにてクラスタに接続を行ってください。

```
spring-boot-sample>kubectl apply -f kubernetes
configmap "spring-boot-config" created
deployment "spring-boot-sample" created
service "spring-boot-sample" created
spring-boot-sample>
```
