# Breaking things like a monkey :)

Hi there

In this repository you'll find some labs that may let you have a better understanding on how to perfom chaos engineering.
Now, let's get started.

# Feedback is welcome

We really appreciate constructive feedback. So you are more than welcome if you want to add some info or comment on this repository.

# Goal

The main goal of these labs is to have a better understanding of how to emulate unexpected behaviours to understand the impact on your applications or group of applications using some open source tools.
Building these labs will let you have a first hand real experience on how these techniques may help you in a daily basis.

Once you finish these labs, you should be able to decide whether this techniques are useful for you.

## What this labs are not

This repository contains simple labs.
Please, remember that chaos experiments may be very complex and that depends on how you design them.

The content of this repository is not intended to tell how you should do your job; it's only purpose is to provide you with some information and real experience to let you decide on your own.

# Requirements

The lab environment is created using _[Kind](https://kind.sigs.k8s.io/)_, but you may use any other _Kubernetes_ cluster if you have one already available for you.
Also, even it's not mandatory, if you already have some knowledge about _[Kubernetes](https://kubernetes.io/)_ it may help.

## Tools

* _Linux OS:_ Actually we are using _[Debian](https://www.debian.org/)_, but any linux distro will do the job.
* _[Kind](https://kind.sigs.k8s.io):_ Used to create a local _[Kubernetes](https://kubernetes.io/)_ cluster.
* _[Linkerd](https://linkerd.io/):_ this is a very lightweight, fast and reliable service mesh tool by _[Buoyant, Inc](https://buoyant.io)_.
* _[Chaos Mesh](https://chaos-mesh.org/):_ an awesome chaos engineering tool for kubernetes from the _[CNCF Sandbox](https://landscape.cncf.io/selected=chaos-mesh)_.

# Useful documentation

Below there is a list of some documentation that may help during these labs.

* *[Kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/)*
* *[Linkerd Starting Guide](https://linkerd.io/2/getting-started/)*
* *[Chaos Mesh Starting guide for Kind](https://chaos-mesh.org/docs/get_started/get_started_on_kind/):* it's a bit different from the standard starting guide because _[Kind](https://kind.sigs.k8s.io)_ uses _containerd_ instead of _docker_.
* *[Kubernetes CRDs documentation](https://kubernetes.io/docs/tasks/extend-kubernetes/custom-resources/custom-resource-definitions/)*

All the software above is used either to set up the lab or to practice with its configuration.

# Folder structure

You'll find following files and directory structure:

* _README.md_: It's this file. Congrats!
* _linkerd folder_: It contains some _[kubernetes](https://kubernetes.io)_ manifests to install _[linkerd](https://linkerd.io)_ and the testing webapp called _emojivoto_.
* _chaos-mesh folder_: You'll find _[chaos mesh](https://chaos-mesh.org)_ installation manifests for _[kind](http://kind.sigs.k8s.io)_.
* _chaos-mesh/experiments folder_: There are some chaos experiments used for this demo and some explanations about them.

# Set the lab

## Setting up from scratch

You will only need to run the following commands:

``` bash
$ # Create a new kubernetes cluster using kind.
$ kind create cluster -name chaos

$ # Install kind and chaos-mesh. The command below will install kind, create a cluster and deploy chaos-mesh into the cluster.
$ curl -sSL https://mirrors.chaos-mesh.org/v1.0.1/install.sh | bash -s -- --template --local kind | kubectl apply -f

$ # Download linkerd binary.
$ wget -O /tmp/linkerd https://github.com/linkerd/linkerd2/releases/download/stable-2.9.0/linkerd2-cli-stable-2.9.0-linux-amd64
$ chmod +x /tmp/linkerd
$ sudo mv /tmp/linkerd /usr/local/bin

$ # Check and install linkerd into the k8s cluster.
$ linkerd check --pre
$ linkerd install | kubectl apply -f -
```

## Setting up using manifests from this demo

If you already have a _Kubernetes_ cluster available, the you will only need to apply some manifests from this repository.

``` bash
$ # Install chaos-mesh.
$ kubectl apply -f chaos-mesh/kind-install-chaos-mesh.yaml

$ # Install linkerd.
$ kubectl apply -f linkerd/linkerd-install.yaml
```

## Installing Emojivoto demo app

``` bash
$ kubectl apply -f linkerd/emojivoto.yaml
```

## Inject linkerd sidecars into emojivoto deployments

``` bash
$ kubectl get -n emojivoto deploy | linkerd inject - | kubectl apply -f -
```

# Acknowledgements, mentions and thanks

