Login to ECR and pass creds to podman

```
aws ecr get-login-password \
--no-verify-ssl \
--region awsregion | \
podman login -u AWS \
--password-stdin \
"awsaccountnumber.dkr.ecr.awsregion.amazonaws.com"
```

