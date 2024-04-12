# Crossplane in a box

Quickstart for AWS

Create `aws-creds.conf`
```
aws_access_key_id=$AWS_ACCESS_KEY_ID
aws_secret_access_key=$AWS_SECRET_ACCESS_KEY
aws_session_token=$AWS_SESSION_TOKEN
```

Create kubernetes secret (local only)
```
kubectl create secret \
       generic aws-secret \
       -n crossplane-system \
       --from-file=creds=./aws-creds.conf
```

Install AWS Provider(s)
```
kubectl apply -Rf yaml/aws/
```

[Blog Post](https://blog.upbound.io/crossplane-development-setup)

![crossplane-in-box](http://www.plantuml.com/plantuml/proxy?cache=yes&src=https://raw.githubusercontent.com/Piotr1215/dca-prep-kit/master/diagrams/local-crossplane-box.puml&fmt=png)
