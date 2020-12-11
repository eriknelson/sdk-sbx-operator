# sdk-sbx-operator

Hello world operator

https://sdk.operatorframework.io/docs/building-operators/ansible/quickstart/

**init**

```
mkdir sdk-sbx; cd sdk-sbx
operator-sdk init --plugins=ansible --domain=operators.nsk.io
```

**create api (CRD)**

```
operator-sdk create api --group sdk-sbx --version v1 --kind Instance --generate-role
```

Just created a basic namespace template to say hello

**build and push operator image**

```
make docker-build docker-push IMG=quay.io/eriknelson/sdk-sbx-operator
```
