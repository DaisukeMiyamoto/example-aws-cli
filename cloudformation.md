CloudFormation
---

# create stack

## base

```
$ aws cloudformation create-stack --stack-name myteststack --template-body file://cloudformation_templates/ec2.yaml
```

## use parameters

```
$ aws cloudformation create-stack --stack-name myteststack --template-body file:///home/testuser/mytemplate.json --parameters ParameterKey=Parm1,ParameterValue=test1 ParameterKey=Parm2,ParameterValue=test2
```

# list

```
$ aws cloudformation list-stacks
```

# describe

```
$ aws cloudformation describe-stacks --stack-name myteststack
```

# delete

```
$ aws cloudformation delete-stack --stack-name myteststack
```
