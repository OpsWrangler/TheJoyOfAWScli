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

Add Fargate capacity to an existing cluster

```
aws ecs put-cluster-capacity-providers \
--cluster cluster_name \
--capacity-providers FARGATE FARGATE_SPOT \
--default-capacity-provider-strategy \
capacityProvider=FARGATE,weight=1,base=1 \
capacityProvider=FARGATE_SPOT,weight=4
```
