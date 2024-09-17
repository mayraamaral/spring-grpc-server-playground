# Spring + gRPC server playground
## Running
Open the terminal in the repository root folder, and then execute the following command:
```shell
./mvnw spring-boot:run
```
PS.: if you face permission issues, just run the command bellow, and then run the command above after again.
```shell
chmod +x mvnw
```
## Requesting
You need to have a gRPC client (like Postman or gRPCurl) to be able to make requests. In this example, we are going to use
gRPCurl.
### Installing gRPCurl - 64 bits machines
First, you need to download it.
```shell
wget https://github.com/fullstorydev/grpcurl/releases/download/v1.9.1/grpcurl_1.9.1_linux_amd64.deb
```
Then you can install it with the following command:
```shell
sudo dpkg -i grpcurl_1.9.1_linux_amd64.deb
```
Note: if this isn't the latest version of gRPCurl nor you use ARM architecture, [consult the official repo for installing instructions](https://github.com/fullstorydev/grpcurl).
### Query parameters

| Parameter | Type   | Description                             |
| --------- | ------ | --------------------------------------- |
| `name`    | String | The name of the person to greet. (Required) |

### Request example
```bash
grpcurl -plaintext -d '{"name": "Mayra"}' localhost:9090 playground.grpcserver.HelloWorldService/greet
```
### Response example
```json
{
  "greeting": "Hello, Mayra"
}
```

References:
- [Docs](https://grpc.io/docs/languages/java/basics/)
- [Baeldung's Introduction to gRPC with Spring Boot](https://www.baeldung.com/spring-boot-grpc)