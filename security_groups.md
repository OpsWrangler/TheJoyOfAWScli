Describe security group rules

```bash
aws ec2 describe-security-group-rules \
    --filter Name="group-id",Values="sg-00000" \
    --output=table
```

Add security group rule
(Replace protocol / port values here with `-1` to indicate 'all')
(Replace `ingress` with `egress` if needed)

```bash
aws ec2 authorize-security-group-ingress \
    --group-id sg-0000000 \
    --protocol tcp \
    --port 80 \
    --cidr 0.0.0.0/0
```
 