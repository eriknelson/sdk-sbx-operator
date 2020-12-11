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

**build and push operator image**

```
make docker-build docker-push IMG=quay.io/eriknelson/sdk-sbx-operator:0.0.1
```

**create bundle metadata**

`make bundle DEFAULT_CHANNEL=main IMG=quay.io/eriknelson/sdk-sbx-operator:0.0.1`

Fill in questions

**Build bundle image and push**

```
make bundle-build BUNDLE_IMG=quay.io/eriknelson/sdk-sbx-operator-bundle:0.0.1
docker push quay.io/eriknelson/sdk-sbx-operator-bundle:0.0.1
```

**Deploy index image, catalogsource, and operator**

`osdk run bundle quay.io/eriknelson/sdk-sbx-operator-bundle:0.0.1`