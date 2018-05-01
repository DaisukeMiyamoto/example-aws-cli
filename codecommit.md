CodeCommit
---

# create new repository

```
aws codecommit create-repository --repository-name test-repo --repository-description "test repository"
```

# git crediential helper

```
git config --global credential.helper '!aws codecommit credential-helper $@'
git config --global credential.UseHttpPath true
```


