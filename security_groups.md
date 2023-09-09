### Add inbound port based rule for everyone
```
aws ec2 authorize-security-group-ingress 
    --group-id sg-0000000 \
    --protocol tcp \
    --port 80 \
    --cidr 0.0.0.0/0
```
