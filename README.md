# Beyond rolling update

Hi there

In this repository you'll find some labs that may let you have a better understanding on how to perfom a bit complex application updates.
Now, let's get started.

# Feedback is welcome

We really appreciate constructive feedback. So you are more than welcome if you want to add some info or comment on this repository.

# Goal

The main goal of these labs is to have a better understanding of how to manage application upgrades in a more controlled and automated manner using some open source tools.
Building these labs will let you have a first hand real experience on how these techniques may help you in a daily basis.

Once you finish these labs, you should be able to decide whether this upgrade techniques are useful for you.

## What this labs are not

This repository contains simple labs.
Please, remember that upgrade workflows may be very complex and that depends on hwo you manage them.

The content of this repository is not intended to tell how you should do your job; it's only purpose is to provide you with some information and real experience to let you decide on your own.

# Requirements

The lab environment is created using _[Kind](https://kind.sigs.k8s.io/)_, but you may use any other _Kubernetes_ cluster if you have one already available for you.
Also, even it's not mandatory, if you already have some knowledge about _[Kubernetes](https://kubernetes.io/)_ it may help.

## Tools

* _Linux OS:_ Actually we are using _[Debian](https://www.debian.org/)_, but any linux distro will do the job.
* _[Kind](https://kind.sigs.k8s.io):_ Used to create a local _[Kubernetes](https://kubernetes.io/)_ cluster.
* _[ArgoCD](https://argoproj.github.io/argo-cd/):_ this is an awesome tool by _[Intuit](https://opensource.intuit.com/app/intuit-open-source/open-source)_ belongs to the _[Argo Project](https://argoproj.github.io/)_ and is used to manage continuous deployment based on a _[GitOps](https://www.gitops.tech/)_ philosophy.
* _[Argo Rollouts](https://argoproj.github.io/argo-rollouts/):_ it complements some of the _[Argo Project](https://argoproj.github.io/)_ tools and provides some complex deployment patterns.

# Useful documentation

Below there is a list of some documentation that may help during these labs.

* _[Kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/)_
* _[ArgoCD getting started guide](https://argoproj.github.io/argo-cd/getting_started/)_
* _[Argo Rollouts installation guide](https://argoproj.github.io/argo-rollouts/installation/)_
* _[Kubernetes CRDs documentation](https://kubernetes.io/docs/tasks/extend-kubernetes/custom-resources/custom-resource-definitions/)_

All the software above is used either to set up the lab or to practice with its configuration.

# Labs folder structure

You'll find some labs in this repository. Each lab has the following file/directory structure:

* _README.md_: to explain the lab and its contents and details.
* _Configuration folders_: you may find some folders which contain configuration files for each tool used in the laboratory. For example an _envoy_ or _consul_ folder with some configuration files that you should use in the lab to run them.

Right now this repository have the labs listed below:


# Set the lab

You will only need to run the following command:

``` bash
```


# Acknowledgements, mentions and thanks

