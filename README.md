# simplekubebuilder
// TODO(user): Add simple overview of use/purpose
```
example : https://cloudyuga.guru/hands_on_lab/kubebuilder-intro
```

## Description
// TODO(user): An in-depth paragraph about your project and overview of use

## Getting Started
You’ll need a Kubernetes cluster to run against. You can use [KIND](https://sigs.k8s.io/kind) to get a local cluster for testing, or run against a remote cluster.
**Note:** Your controller will automatically use the current context in your kubeconfig file (i.e. whatever cluster `kubectl cluster-info` shows).

### Running on the cluster
1. 명세서 생성해주기 (config/crd/bases에 생성 됨 - CRD yaml 파일)
```sh
$ make manifest
```
2. Local 쿠버네티스 클러스터에 CRD 등록하기
```sh
$ make install
$ kubectl get crds
NAME                             CREATED AT
demoresources.demo.demo.kcd.io   2023-10-01T07:22:22Z
```
3. CRD를 참고하여 작성한 yaml 파일 기반 CR을 쿠버네티스에 적용
```sh
# spec에 변수 값 써주기
$ kubectl apply -k config/samples/demo_v1_demoresource.yaml
```

### Uninstall CRDs
To delete the CRDs from the cluster:

```sh
# CRD 삭제 됨
make uninstall
```

## Contributing
// TODO(user): Add detailed information on how you would like others to contribute to this project

### How it works
This project aims to follow the Kubernetes [Operator pattern](https://kubernetes.io/docs/concepts/extend-kubernetes/operator/).

It uses [Controllers](https://kubernetes.io/docs/concepts/architecture/controller/),
which provide a reconcile function responsible for synchronizing resources until the desired state is reached on the cluster.

### Test It Out
1. Install the CRDs into the cluster:

```sh
make install
```

2. Run your controller (this will run in the foreground, so switch to a new terminal if you want to leave it running):

```sh
make run
```

**NOTE:** You can also run this in one step by running: `make install run`

### Modifying the API definitions
If you are editing the API definitions, generate the manifests such as CRs or CRDs using:

```sh
make manifests
```

**NOTE:** Run `make --help` for more information on all potential `make` targets

More information can be found via the [Kubebuilder Documentation](https://book.kubebuilder.io/introduction.html)

## License

Copyright 2023.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

