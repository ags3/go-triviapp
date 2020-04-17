# Triviapp

**Is a web application that will give you fun trivia related to today's date. The Application consists of REST API backend and SSR frontend. Both applications are written using GoLang.**

## Helm Chart

You can easily deploy the application to the Kubernetes cluster using Helm Package Manager. The helm chart is included in this repository. To make your life even easier I also add Makefile. Hence, you can use make command to install, uninstall, plan, test, and etc

### Makefile Manual

This makefile is intended to make installing, uninstalling, scale up, scale down, & test Triviapp more easier and consistent.

In Order to run everything correctly,

- Make sure that you have kubectl & helm Installed

- The kubernetes cluster is up and running, you can try "kubectl get nodes" to find out

#### Command List

- **help** -- Sort of manual to help you proceed

- **install** -- Installing Triviapp using Helm Package Manager

- **upgrade** -- Upgrading Triviapp using Helm Package Manager

- **plan** -- Plan installation and show the generated kubernetes configuration

- **uninstall** -- Uninstalling Triviapp using Helm Package Manager

- **list** -- List all application installed by Helm Package Manager

- **kube-list** -- List all active pod, deployment, replicaset, and service in kubernetes cluster

- **test** -- Test connection to frontend and backend application, to make sure application installed properly

#### Parameter List

- **namespace** -- Designated namespace where Helm install the application [default:default]

- **appname** -- Prefix Name for Triviapp [default:lmnzr]

- **frontendtype** -- Service type for frontend application (ClusterIP,NodePort,LoadBalancer) [default:NodePort]

- **frontendcount** -- Replication count for frontend application [default:1]

- **backendcount** -- Replication count for backend application [default:1]

#### Usage Example

Simple Installation

```
make install
```

Installation With LoadBalancer Type

```
make install frontendtype=LoadBalancer
```

Scale Up Application

```
make upgrade frontendcount=3 backendcount=5
```

Scale Down Application

```
make upgrade frontendcount=1
```

Uninstall

```
make uninstall
```

## Backend Application

[More Info Here](https://github.com/lmnzr/go-triviapp/tree/master/backend)

## FrontEnd Application

[More Info Here](https://feature-api-dev.halofina.com/kyc)
