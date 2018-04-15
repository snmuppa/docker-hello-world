## Hello world docker project with Spring Boot.

## Project credits:
https://howtodoinjava.com/docker/docker-hello-world-example/


## Deploying the container to AWS Fargate

* Create IAM Role `EcsTaskExecutionRole` with `AmazonECSTaskExecutionRolePolicy`

* Register task-definition

```
aws ecs register-task-definition --cli-input-json file://aws-ecs/task.json

```

* Create a service with the `task` created in step #2

```
aws ecs create-service --cli-input-json file://aws-ecs/service.json
```

* If the you have updated the task definition then update the service

```
aws ecs update-service --service helloworld-fargate-service --cluster hello_world-test --task helloworld-task

```
