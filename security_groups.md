Create security group

```sh
aws ec2 create-security-group \
--group-name name \
--description description \
--vpc-id vpc-0000
```

Describe security group rules

```sh
aws ec2 describe-security-group-rules \
    --filter Name="group-id",Values="sg-00000" \
    --output=table
```

Add security group rule
(Replace protocol / port values here with `-1` to indicate 'all')
(Replace `ingress` with `egress` if needed)
(Replace `cidr` with `source-group` for sg to sg)

```sh
aws ec2 authorize-security-group-ingress \
    --group-id sg-0000000 \
    --protocol tcp \
    --port 80 \
    --cidr 0.0.0.0/0
```
 
Remove security group rule

```sh
aws ec2 revoke-security-group-ingress  \
    --group-id sg-00000 \
    --security-group-rule-ids sgr-0000
```
