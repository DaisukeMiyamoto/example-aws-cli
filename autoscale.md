Autoscaling
---


# create launch config

```
$ aws autoscaling create-launch-configuration --launch-configuration-name config1 --image-id ami-d874e0a0 --instance-type t2.micro
```

# create autoscaling group

```
$ aws autoscaling create-auto-scaling-group --auto-scaling-group-name autoscale1 --launch-configuration-name config1 --min-size 2 --max-size 4 --desired-capacity 2 --availability-zones "us-west-2a" "us-west-2b"
```

# check

```
$ aws autoscaling describe-auto-scaling-groups
```

# delete

```
$ aws autoscaling delete-auto-scaling-group --auto-scaling-group-name autoscale1
```
