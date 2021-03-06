Start EC2 by CLI
---


# add Security Group

```
$ aws ec2 create-security-group --group-name ssh-sg --description "security group for SSH in EC2"
$ aws ec2 authorize-security-group-ingress --group-name ssh-sg --protocol tcp --port 22 --cidr 0.0.0.0/0
```

# add Key Pair

```
$ aws ec2 create-key-pair --key-name main-key --query 'KeyMaterial' --output text > main-key.pem
$ chmod 600 main-key.pem
```

# Launch

```
$ aws ec2 run-instances --image-id ami-d874e0a0 --security-groups ssh-sg --count 1 --instance-type t2.micro --key-name main-key --tag-specifications 'ResourceType=instance,Tags=[{Key=Name,Value=ec2-cli}]' --query 'Instances[0].InstanceId'
"i-0a26a6d6b0dddc87d"
```

# Get Public IP
```
$ aws ec2 describe-instances --instance-ids "i-0a26a6d6b0dddc87d" --query 'Reservations[0].Instances[0].PublicIpAddress'
52.42.105.83
```

# Connect

```
$ ssh -i main-key.pem ec2-user@52.42.105.83
```

# Terminate

```
$ aws ec2 terminate-instance --instance-ids "i-0a26a6d6b0dddc87d"
```
