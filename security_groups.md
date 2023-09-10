### Describe security group rules
```
aws ec2 describe-security-group-rules \
    --filter Name="group-id",Values="sg-00000"
    --output=table
```

### Add inbound port based rule

```
aws ec2 authorize-security-group-ingress \
    --group-id sg-0000000 \
    --protocol tcp \
    --port 80 \
    --cidr 0.0.0.0/0
```

### Add 