Turn on ECS Exec for a service

```
aws ecs update-service \
--cluster clustername \
--service servicename \
--enable-execute-command \
--force-new-deployment
```

Open a shell on a running container

```
aws ecs execute-command \
--cluster cluster_name \
--task taskID \
--container container_name \
--interactive \
--command "/bin/sh"
```

Export (download) a file from a running container

```
aws ecs execute-command \
--cluster cluster_name \
--task taskID \
--container container_name \
--interactive \
--command "cat filename_on_container" >> \
filename_on_local_machine
```

Describe cluster

```
aws ecs describe-clusters --cluster cluster_name
```

Replace existing cluster with Fargate capacity provider, using FARGATE_SPOT primarily
- The `base` value sets how many tasks will run for that CP, after that base is filled then the weight goes into effect as a balancing strategy

```
aws ecs put-cluster-capacity-providers \
--cluster cluster_name \
--capacity-providers FARGATE FARGATE_SPOT \
--default-capacity-provider-strategy \
capacityProvider=FARGATE_SPOT,weight=1,base=10 \
capacityProvider=FARGATE,weight=4
```
