kube day 1
----------

Topics

* Requirements
* Introduction
* Goals
* Kubernetes Distros
* Openshift
* Lab 1 Install oc client and log into Openshift cluster
* Openshift Documentation
* Lab 2 Deploy an app to your namespace

requirements
------------

* Basic understanding of Kubernetes and Docker
* Be able to read and understand everything in this children’s picture book: https://www.cncf.io/phippy-goes-to-the-zoo-book/
* Can install Openshift client binaries on windows/linux/mac
* Can install Helm binary on windows/linux/mac
* Recommend having Docker installed with Kubernetes enabled
* Optionally have [code ready containers](https://developers.redhat.com/products/codeready-containers/overview) installed for local openshift development
* Show up everyday by 7:05. Alert me or attempt to make it up otherwise
* Time on shared cluster after class must be scheduled in slack in set increments. Otherwise the cluster will be turned off everyday to save costs. Try to piggy back on other students scheduled time (See slack channel).

introductions
-------------

* Keep it quick
* Who are you?
* What do you do?
* What do you want to do with Kubernetes?

goals of this course
--------------------

* Master Kubernetes basics
* Learn Openshift
* Learn about non-core components that support Kubernetes environments
* Start walking down the [cloud native trail](https://github.com/cncf/landscape/blob/master/README.md#trail-map)
* Be able to administer an Openshift/Kubernetes cluster

important items provided by kubernetes distros
----------------------------------------------

* User management
* Better than vanilla UI
* Improved default security
* Docker Registry
* Observability Solutions - Metrics/Tracing/Logging
* Service Mesh
* Multi-cluster
* CI/CD
* GitOps
* Fully automated installation tools
* Immutable container OS
* Functions as a Service
* Usually a new addition to this list each year

software distros
----------------

Software distros can be run locally or in the cloud. They are the least likely to lock you in.

* Vanilla Kubernetes
    * Developed by CNCF
    * Purest, most up to date form of Kubernetes
    * Requires the user to choose their own non-core features
    * Requires the user to choose an OS

* Openshift/CoreOS
    * Developed by RedHat
    * THE turn key kubernetes distro. RedHat has put together a verified solution for every non-core Kubernetes feature out there.
    * The one software distro that might lock you in if you aren’t careful. (At least it’s multi-cloud)
    * RedHat deviates/forks CNCF projects including Kubernetes itself
    * Immutable container OS

* Rancher OS
    * Developed by Rancher
    * Better than Vanilla for non-core features
    * Non-core features are pure CNCF implementations. No forking.
    * Tracks Vanilla closely
    * Avoids lock in concerns
    
All other distros are mostly just managed/packaged versions of Vanilla with a spin on the UI.


cloud distros
-------------

Cloud distros are mostly just managed versions of Vanilla Kubernetes. They all share 1 click deployments and preselected OS images. All cloud distros are designed to lock you in by encouraging you to consume cloud specific services. Stick with compute and block storage to avoid this. The one notable cloud distro is AWS EKS Fargate which really isn’t a Kubernetes distro but rather an implementation of the Kubernetes API which interacts with the Fargate system. It runs containers as micro-vms.

Top cloud distros

* [AWS EKS](https://aws.amazon.com/eks/)
* [AWS EKS Fargate](https://docs.aws.amazon.com/eks/latest/userguide/fargate.html)
* [Google GKE](https://cloud.google.com/kubernetes-engine/docs/concepts/kubernetes-engine-overview)
* [Azure AKS](https://azure.microsoft.com/en-us/overview/kubernetes-on-azure/)
* [Openshift Dedicated on AWS](https://www.openshift.com/products/dedicated/)
* All the other clouds

oc client
---------

1. Install the Openshift oc client
    * Pick the binary for your platform from the [okd release page](https://github.com/openshift/okd/releases/tag/4.5.0-0.okd-2020-09-04-180756) and put it in your PATH
        * [Mac](https://github.com/openshift/okd/releases/download/4.5.0-0.okd-2020-09-04-180756/openshift-client-mac-4.5.0-0.okd-2020-09-04-180756.tar.gz)
        * [Windows](https://github.com/openshift/okd/releases/download/4.5.0-0.okd-2020-09-04-180756/openshift-client-windows-4.5.0-0.okd-2020-09-04-180756.zip)
        * [Linux](https://github.com/openshift/okd/releases/download/4.5.0-0.okd-2020-09-04-180756/openshift-client-linux-4.5.0-0.okd-2020-09-04-180756.tar.gz)
        * Mac homebrew - `brew install openshift-cli`
    * Log into the class Openshift cluster
    * See class Slack for credentials
2. Log in on the command line `oc login`
    * Run `oc get nodes`
    * Log into the Web UI
3. Create a project/namespace that matches your name
last name + first initial e.g. Timothy Allen = timothya

openshift 4 documentation
-------------------------

Get comfortable with the openshift 4 documentation as it will guide  you as both a developer and admin.

* [Openshift 4.5 Docs](https://docs.openshift.com/container-platform/4.5/welcome/index.html)

deploy an app
-------------

* Deploy an app to your namespace
* Use whatever method you would like. 
* Bonus points if you can hit your application via route.

Links
* [Create an App](https://docs.openshift.com/container-platform/4.5/applications/application_life_cycle_management/creating-applications-using-cli.html)
* [Expose a Servie](https://docs.openshift.com/container-platform/4.5/cli_reference/openshift_cli/developer-cli-commands.html#expose)
