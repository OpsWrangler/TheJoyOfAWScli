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
