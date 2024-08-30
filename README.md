# devopslab


This repo contains the example used for experience different technology for Kubernetes cluster

## Getting started

### Prerequisite
These software need to be installed and well setup in local machine
- [Nix shell](https://nixos.org/download/#download-nix)
- [Direnv](https://direnv.net/)

### 1. Install software

Navigate to the repo folder, all software will be automatically installed by direnv and nix setup

```
~/p/dzungtr> cd cncflab/
direnv: loading ~/project/dzungtr/cncflab/.envrc
direnv: using nix
direnv: export <SOME env var>
```

List of softwares installed can be tracked in `default.nix` file. The lab uses `kind` as k8s cluster distribution to set up local easily. More information, you can reference here https://kind.sigs.k8s.io/

### 2. Start applications

```shell
# create k8s cluster
kind create cluster --config k8s-distribution/kind/cni-disable.yml

# Install Cilium
kustomize build network/cilium --enable-helm | kubectl apply -f -
```

![tilt up](./assets/tiltup.png)

