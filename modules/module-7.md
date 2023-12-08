---
description: Azure Container Services
---

# 💡 Module 7

## Azure Container Services

Before jumping over ACS let's understand the few more topics&#x20;

## What is a container? <a href="#what-is-a-container" id="what-is-a-container"></a>

A container is a loosely isolated environment that allows us to build and run software packages. These software packages include the code and all dependencies to run applications quickly and reliably on any computing environment. We call these packages _container images_.

The container image becomes the unit we use to distribute our applications.

## Containers vs. virtual machines <a href="#containers-vs-virtual-machines" id="containers-vs-virtual-machines"></a>

### Container architecture <a href="#container-architecture" id="container-architecture"></a>

A container is an isolated, lightweight silo for running an application on the host operating system. Containers build on top of the host operating system's kernel (which can be thought of as the buried plumbing of the operating system), and contain only apps and some lightweight operating system APIs and services that run in user mode, as shown in this diagram.

<figure><img src="../.gitbook/assets/image (21) (1).png" alt=""><figcaption></figcaption></figure>

### Virtual machine architecture <a href="#virtual-machine-architecture" id="virtual-machine-architecture"></a>

In contrast to containers, VMs run a complete operating system–including its own **kernel**–as shown in this diagram.

<figure><img src="../.gitbook/assets/image (22) (1).png" alt=""><figcaption></figcaption></figure>

| Feature                               | Virtual machine                                                                                                                                                                                                                      | Container                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Isolation                             | Provides complete isolation from the host operating system and other VMs. This is useful when a strong security boundary is critical, such as hosting apps from competing companies on the same server or cluster.                   | Typically provides lightweight isolation from the host and other containers, but doesn't provide as strong a security boundary as a VM. (You can increase the security by using [Hyper-V isolation mode](https://learn.microsoft.com/en-us/virtualization/windowscontainers/manage-containers/hyperv-container) to isolate each container in a lightweight VM).                                                                                                                                                                                                                                                                                            |
| Operating system                      | Runs a complete operating system including the kernel, thus requiring more system resources (CPU, memory, and storage).                                                                                                              | Runs the user mode portion of an operating system, and can be tailored to contain just the needed services for your app, using fewer system resources.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Guest compatibility                   | Runs just about any operating system inside the virtual machine                                                                                                                                                                      | Runs on the [same operating system version as the host](https://learn.microsoft.com/en-us/virtualization/windowscontainers/deploy-containers/version-compatibility) (Hyper-V isolation enables you to run earlier versions of the same OS in a lightweight VM environment)                                                                                                                                                                                                                                                                                                                                                                                 |
| Deployment                            | Deploy individual VMs by using Windows Admin Center or Hyper-V Manager; deploy multiple VMs by using PowerShell or System Center Virtual Machine Manager.                                                                            | Deploy individual containers by using Docker via command line; deploy multiple containers by using an orchestrator such as Azure Kubernetes Service.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Operating system updates and upgrades | Download and install operating system updates on each VM. Installing a new operating system version requires upgrading or often just creating an entirely new VM. This can be time-consuming, especially if you have a lot of VMs... | <p>Updating or upgrading the operating system files within a container is the same:<br></p><ol><li>Edit your container image's build file (known as a Dockerfile) to point to the latest version of the Windows base image.</li><li>Rebuild your container image with this new base image.</li><li>Push the container image to your container registry.</li><li>Redeploy using an orchestrator.<br>The orchestrator provides powerful automation for doing this at scale. For details, see <a href="https://learn.microsoft.com/en-us/azure/aks/tutorial-kubernetes-app-update">Tutorial: Update an application in Azure Kubernetes Service</a>.</li></ol> |
| Persistent storage                    | Use a virtual hard disk (VHD) for local storage for a single VM, or an SMB file share for storage shared by multiple servers                                                                                                         | Use Azure Disks for local storage for a single node, or Azure Files (SMB shares) for storage shared by multiple nodes or servers.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Load balancing                        | Virtual machine load balancing moves running VMs to other servers in a failover cluster.                                                                                                                                             | Containers themselves don't move; instead an orchestrator can automatically start or stop containers on cluster nodes to manage changes in load and availability.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Fault tolerance                       | VMs can fail over to another server in a cluster, with the VM's operating system restarting on the new server.                                                                                                                       | If a cluster node fails, any containers running on it are rapidly recreated by the orchestrator on another cluster node.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Networking                            | Uses virtual network adapters.                                                                                                                                                                                                       | Uses an isolated view of a virtual network adapter, providing a little less virtualization–the host's firewall is shared with containers–while using less resources. For more, see [Windows container networking](https://learn.microsoft.com/en-us/virtualization/windowscontainers/container-networking/architecture).                                                                                                                                                                                                                                                                                                                                   |

## What is software containerization? <a href="#what-is-software-containerization" id="what-is-software-containerization"></a>

Software containerization is an OS-virtualization method used to deploy and run containers without using a virtual machine (VM). Containers can run on physical hardware, in the cloud, on VMs, and across multiple operating systems.

### What is Docker? <a href="#what-is-docker" id="what-is-docker"></a>

Docker is a containerization platform used to develop, ship, and run containers. Docker doesn't use a hypervisor, and you can run Docker on your desktop or laptop if you're developing and testing applications. The desktop version of Docker supports Linux, Windows, and macOS. For production systems, Docker is available for server environments, including many variants of Linux and Microsoft Windows Server 2016 and above. Many clouds, including Azure, support Docker.

## Docker Engine

The Docker Engine consists of several components configured as a client-server implementation where the client and server run simultaneously on the same host. The client communicates with the server using a REST API, which enables the client to also communicate with a remote server instance.

\


<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

**The Docker client**

There are two alternatives for Docker client: A command-line application named `docker` or a Graphical User Interface (GUI) based application called Docker Desktop. Both the CLI and Docker Desktop interact with a Docker server. The `docker` commands from the CLI or Docker Desktop use the Docker REST API to send instructions to either a local or remote server and function as the primary interface we use to manage our containers.

**The Docker server**

The Docker server is a daemon named `dockerd`. The `dockerd` daemon responds to requests from the client via the Docker REST API and can interact with other daemons. The Docker server is also responsible for tracking the lifecycle of our containers.

**Docker objects**

There are several objects that you'll create and configure to support your container deployments. These include networks, storage volumes, plugins, and other service objects. We won't cover all of these objects here, but it's good to keep in mind that these objects are items that we can create and deploy as needed.

### Docker Hub <a href="#docker-hub" id="docker-hub"></a>

Docker Hub is a Software as a Service (SaaS) Docker container registry. Docker registries are repositories that we use to store and distribute the container images we create. Docker Hub is the default public registry Docker uses for image management.

### What is a container image? <a href="#what-is-a-container-image" id="what-is-a-container-image"></a>

A container image is a portable package that contains software. It's this image that, when run, becomes our container. The container is the in-memory instance of an image.

A container image is immutable. Once you've built an image, you can't change it. The only way to change an image is to create a new image. This feature is our guarantee that the image we use in production is the same image used in development and QA.

### What is the host OS? <a href="#what-is-the-host-os" id="what-is-the-host-os"></a>

The host OS is the OS on which the Docker engine runs. Docker containers running on Linux share the host OS kernel, and don't require a container OS as long as the binary can access the OS kernel directly.However, Windows containers need a container OS. The container depends on the OS kernel to manage services such as the file system, network management, process scheduling, and memory management.

\


<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

## What is the container OS? <a href="#what-is-the-container-os" id="what-is-the-container-os"></a>

The container OS is the OS that's part of the packaged image. We have the flexibility to include different versions of Linux or Windows operating systems in a container. This flexibility allows us to access specific OS features or install additional software our applications might use.

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

The container OS is isolated from the host OS, and it's the environment in which we deploy and run our application. Combined with the image's immutability, this isolation means the environment for our application running in development is the same as in production.

## What is the Stackable Unification File System (`Unionfs`)? <a href="#what-is-the-stackable-unification-file-system-unionfs" id="what-is-the-stackable-unification-file-system-unionfs"></a>

`Unionfs` is a filesystem that allows you to stack several directories—called branches—in such a way that it appears as if the content is merged. However, the content is physically kept separate. `Unionfs` allows you to add and remove branches as you build out your file system.

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

## What is a base image? <a href="#what-is-a-base-image" id="what-is-a-base-image"></a>

A base image is an image that uses the Docker `scratch` image. The `scratch` image is an empty container image that doesn't create a filesystem layer. This image assumes that the application you're going to run can directly use the host OS kernel.

### What is a parent image? <a href="#what-is-a-parent-image" id="what-is-a-parent-image"></a>

A parent image is a container image from which you create your images.

For example, instead of creating an image from `scratch` and then installing Ubuntu, we'll use an image already based on Ubuntu. We can even use an image that already has nginx installed. A parent image usually includes a container OS.

## What is the main difference between base and parent images?

Both image types allow us to create a reusable image. However, base images allow us more control over the final image contents. Recall from earlier that an image is immutable; you can only add to an image and not subtract.

On Windows, you can only create container images that are based on Windows base container images. Microsoft provides and services these Windows base container images.

## What is a Dockerfile?

A Dockerfile is a text file that contains the instructions we use to build and run a Docker image. The following aspects of the image are defined:

* The base or parent image we use to create the new image
* Commands to update the base OS and install additional software
* Build artifacts to include, such as a developed application
* Services to expose, such as storage and network configuration
* Command to run when the container is launched



```bash
# Step 1: Specify the parent image for the new image
FROM ubuntu:18.04

# Step 2: Update OS packages and install additional software
RUN apt -y update &&  apt install -y wget nginx software-properties-common apt-transport-https \
	&& wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb \
	&& dpkg -i packages-microsoft-prod.deb \
	&& add-apt-repository universe \
	&& apt -y update \
	&& apt install -y dotnet-sdk-3.0

# Step 3: Configure Nginx environment
CMD service nginx start

# Step 4: Configure Nginx environment
COPY ./default /etc/nginx/sites-available/default

# STEP 5: Configure work directory
WORKDIR /app

# STEP 6: Copy website code to container
COPY ./website/. .

# STEP 7: Configure network requirements
EXPOSE 80:8080

# STEP 8: Define the entry point of the process that runs in the container
ENTRYPOINT ["dotnet", "website.dll"]
```

The `ENTRYPOINT` in the file indicates which process will execute once we run a container from an image. If there's no ENTRYPOINT or another process to be executed, Docker will interpret that as there's nothing for the container to do, and the container will exit.

## How to manage Docker images <a href="#how-to-manage-docker-images" id="how-to-manage-docker-images"></a>

Docker images are large files that are initially stored on your PC, and we need tools to manage these files.

The Docker CLI and Docker Desktop allow us to manage images by building, listing, removing, and running them. We manage Docker images by using the `docker` client. The client doesn't execute the commands directly, and sends all queries to the `dockerd` daemon.

## How to build an image? <a href="#how-to-build-an-image" id="how-to-build-an-image"></a>

We use the `docker build` command to build Docker images. Let's assume we use the Dockerfile definition from earlier to build an image. Here's an example that shows the build command:

```bash
docker build -t temp-ubuntu .
```

Output:

```bash
Sending build context to Docker daemon  4.69MB
Step 1/8 : FROM ubuntu:18.04
 ---> a2a15febcdf3
Step 2/8 : RUN apt -y update && apt install -y wget nginx software-properties-common apt-transport-https && wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb && dpkg -i packages-microsoft-prod.deb && add-apt-repository universe && apt -y update && apt install -y dotnet-sdk-3.0
 ---> Using cache
 ---> feb452bac55a
Step 3/8 : CMD service nginx start
 ---> Using cache
 ---> ce3fd40bd13c
Step 4/8 : COPY ./default /etc/nginx/sites-available/default
 ---> 97ff0c042b03
Step 5/8 : WORKDIR /app
 ---> Running in 883f8dc5dcce
Removing intermediate container 883f8dc5dcce
 ---> 6e36758d40b1
Step 6/8 : COPY ./website/. .
 ---> bfe84cc406a4
Step 7/8 : EXPOSE 80:8080
 ---> Running in b611a87425f2
Removing intermediate container b611a87425f2
 ---> 209b54a9567f
Step 8/8 : ENTRYPOINT ["dotnet", "website.dll"]
 ---> Running in ea2efbc6c375
Removing intermediate container ea2efbc6c375
 ---> f982892ea056
Successfully built f982892ea056
Successfully tagged temp-ubuntu:latest
```

### How to list images <a href="#how-to-list-images" id="how-to-list-images"></a>

The Docker software automatically configures a local image registry on your machine. You can view the images in this registry with the `docker images` command.

```
docker images
```

## How to remove an image?

You can remove an image from the local docker registry with the `docker rmi` command. This is useful if you need to save space on the container host disk, because container image layers add up to the total space available.

Specify the name or ID of the image to remove. This example removes the image for the sample web app using the image name:

```
docker rmi temp-ubuntu:version-1.0
```

## Docker benefits

### Efficient hardware use

Containers run without using a virtual machine (VM). As we learned, the container relies on the host kernel for functions such as file system, network management, process scheduling, and memory management.

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

### Container isolation

Docker containers provide security features to run multiple containers simultaneously on the same host without affecting each other. As we saw, we can configure both data storage and network configuration to isolate our containers or share data and connectivity between specific containers.

Let's compare this feature to using VMs.\


<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

## Deploying containers in Azure <a href="#deploying-containers-in-azure" id="deploying-containers-in-azure"></a>

Azure provides several options for hosting these containerized workloads:

* Azure Kubernetes Services (AKS)
* Azure Container Instance (ACI)
* Azure Web Apps for Containers

## Azure Container Registry <a href="#azure-container-registry" id="azure-container-registry"></a>

&#x20;Azure Container Registry (ACR) is a fully managed container registry service in the Azure cloud. It persists your images inside the Azure network, reducing the time to deploy them to Azure container hosts. You can also secure them using the same security and identity procedures that you use for other Azure resources.

You create an Azure Container Registry using the [Azure portal](https://learn.microsoft.com/en-us/azure/container-registry/container-registry-get-started-portal), [Azure CLI](https://learn.microsoft.com/en-us/azure/container-registry/container-registry-get-started-azure-cli), or [PowerShell tools](https://learn.microsoft.com/en-us/azure/container-registry/container-registry-get-started-powershell). Creating a registry in Azure is simple. It requires an Azure subscription, resource group, and a unique name. Figure 3-10 shows the basic options for creating a registry, which will be hosted at `registryname.azurecr.io`.

\


<figure><img src="../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

Once you've created the registry, you'll need to authenticate with it before you can use it. Typically, you'll log into the registry using the Azure CLI command:

```
az acr login --name *registryname*
```

Once authenticated, you can use docker commands to push container images to it. Before you can do so, however, you must tag your image with the fully qualified name (URL) of your ACR login server. It will have the format _registryname_.azurecr.io.

```
docker tag mycontainer myregistry.azurecr.io/mycontainer:v1
```

After you've tagged the image, you use the `docker push` command to push the image to your ACR instance.

```
docker push myregistry.azurecr.io/mycontainer:v1
```

After you push an image to the registry, it's a good idea to remove the image from your local Docker environment, using this command:

`docker rmi myregistry.azurecr.io/mycontainer:v1`

## ACR Tasks <a href="#acr-tasks" id="acr-tasks"></a>

ACR Tasks is a set of features available from the Azure Container Registry. It extends your inner-loop development cycle by building and managing container images in the Azure cloud. Instead of invoking a docker build and docker push locally on your development machine, they're automatically handled by ACR Tasks in the cloud.

The following AZ CLI command both builds a container image and pushes it to ACR:

```
# create a container registry
az acr create --resource-group myResourceGroup --name myContainerRegistry008 --sku Basic

# build container image in ACR and push it into your container registry
az acr build --image sample/hello-world:v1  --registry myContainerRegistry008 --file Dockerfile .
```

## Azure Kubernetes Service <a href="#azure-kubernetes-service" id="azure-kubernetes-service"></a>

Before starting AKS , let's understand what is K8S

The decoupled design of microservices combined with the atomicity of containers makes it possible to scale out apps that respond to demand. In complex solutions, like the drone-tracking app, the process of deploying, updating, monitoring, and removing containers introduces challenges.

Kubernetes is a portable, extensible open-source platform for your management and orchestration of containerized workloads. Kubernetes simplifies complex container-management tasks and provides you with declarative configuration to orchestrate containers in different computing environments. This orchestration platform gives you the same ease of use and flexibility you might already know from platform as a service (PaaS) or infrastructure as a service (IaaS) offerings.

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

## What is container management?

Container management is the process of organizing, adding, removing, or updating a significant number of containers.

The drone-tracking app consists of multiple microservices responsible for tasks like caching, queuing, or data processing. Each of these services is hosted in a container that's deployed, updated, and scaled independently from one another.

\


<figure><img src="../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

## What is a container orchestrator? <a href="#what-is-a-container-orchestrator" id="what-is-a-container-orchestrator"></a>

A container orchestrator is a system that automatically deploys and manages containerized apps. As part of management, the orchestrator handles scaling dynamic changes in the environment to increase or decrease the number of deployed instances of the app. It also ensures all deployed container instances are updated when a new version of a service is released.

### Kubernetes benefits <a href="#kubernetes-benefits" id="kubernetes-benefits"></a>

* Self-healing of containers; for example, restarting containers that fail or replacing containers
* Scaling deployed container count up or down dynamically, based on demand
* Automating rolling updates and rollbacks of containers
* Managing storage
* Managing network traffic
* Storing and managing sensitive information such as usernames and passwords

## How Kubernetes works?

### What is a computer cluster? <a href="#what-is-a-computer-cluster" id="what-is-a-computer-cluster"></a>

A cluster is a set of computers that you configure to work together and view as a single system. The computers configured in the cluster handle the same kinds of tasks. For example, they'll all host websites, APIs, or run compute-intensive work.

A cluster uses centralized software that's responsible for scheduling and controlling these tasks. The computers in a cluster that run the tasks are called _nodes_, and the computers that run the scheduling software are called control _planes_.

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

## Kubernetes architecture

Recall from earlier that an orchestrator is a system that deploys and manages apps. You also learned that a cluster is a set of computers that work together and are viewed as a single system. You use Kubernetes as the orchestration and cluster software to deploy your apps and respond to changes in compute resource needs.

<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

A Kubernetes cluster contains at least one main plane and one or more nodes. Both the control planes and node instances can be physical devices, virtual machines, or instances in the cloud. The default host OS in Kubernetes is Linux, with default support for Linux-based workloads.

## Kubernetes control plane

The Kubernetes control plane in a Kubernetes cluster runs a collection of services that manage the orchestration functionality in Kubernetes.

From a learning perspective, it makes sense to use a single control plane in your test environment as you explore Kubernetes functionality. However, in production and cloud deployments such as Azure Kubernetes Service (AKS), you find that the preferred configuration is a high-availability deployment with three to five replicated control planes.\
\
**Kubernetes node**

A node in a Kubernetes cluster is where your compute workloads run. Each node communicates with the control plane via the API server to inform it about state changes on the node.

## Services that run on a control plane

Kubernetes relies on several administrative services running on the control plane. These services manage aspects such as cluster-component communication, workload scheduling, and cluster-state persistence.\


<figure><img src="../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

The following services make up a Kubernetes cluster's control plane:

* API server
* Backing store
* Scheduler
* Controller manager
* Cloud controller manager

#### What is the API server? <a href="#what-is-the-api-server" id="what-is-the-api-server"></a>

You can think of the API server as the front end to your Kubernetes cluster's control plane. All the communication between the components in Kubernetes is done through this API.

This API exposes a RESTful API that you can use to post commands or YAML-based configuration files. YAML is a human-readable, data serialization standard for programming languages. You use YAML files to define the intended state of all the objects within a Kubernetes cluster.

## What is the backing store? <a href="#what-is-the-backing-store" id="what-is-the-backing-store"></a>

The backing store is a persistent storage in which your Kubernetes cluster saves its completed configuration. Kubernetes uses a high-availability, distributed, and reliable key-value store called `etcd`. This key-value store stores the current state and the desired state of all objects within your cluster.

## What is the scheduler? <a href="#what-is-the-scheduler" id="what-is-the-scheduler"></a>

The scheduler is the component that's responsible for the assignment of workloads across all nodes. The scheduler monitors the cluster for newly created containers and assigns them to nodes.

## What is the controller manager? <a href="#what-is-the-controller-manager" id="what-is-the-controller-manager"></a>

The controller manager launches and monitors the controllers configured for a cluster through the API server.

Kubernetes uses controllers to track object states in the cluster. Each controller runs in a nonterminating loop while watching and responding to events in the cluster. For example, there are controllers to monitor nodes, containers, and endpoints.

The controller communicates with the API server to determine the object's state. If the current state is different from the wanted state of the object, the controller takes action to ensure the wanted state.

## What is the cloud controller manager?

The cloud controller manager integrates with the underlying cloud technologies in your cluster when the cluster is running in a cloud environment. These services can be load balancers, queues, and storage, for example.

## Services that run on a node <a href="#services-that-run-on-a-node" id="services-that-run-on-a-node"></a>

The following services run on the Kubernetes node:

* Kubelet
* Kube-proxy
* Container runtime

<figure><img src="../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

## What is the kubelet?

The kubelet is the agent that runs on each node in the cluster and monitors work requests from the API server. It makes sure that the requested unit of work is running and healthy.

The kubelet monitors the nodes and makes sure that the containers scheduled on each node run as expected. The kubelet manages only containers Kubernetes creates. It isn't responsible for rescheduling work to run on other nodes if the current node can't run the work.

## What is kube-proxy?

The kube-proxy component is responsible for local cluster networking, and runs on each node. It ensures that each node has a unique IP address. It also implements rules to handle routing and load balancing of traffic by using iptables and IPVS.

This proxy doesn't provide DNS services by itself. A DNS cluster add-on based on CoreDNS is recommended and installed by default.

## What is the container runtime?

The container runtime is the underlying software that runs containers on a Kubernetes cluster. The runtime is responsible for fetching, starting, and stopping container images. Kubernetes supports several container runtimes, including but not limited to Docker, containerd, rkt, CRI-O, and frakti. The support for many container runtime types is based on the Container Runtime Interface (CRI). The CRI is a plug-in design that enables the kubelet to communicate with the available container runtime.

The default container runtime in AKS is containerd, an industry-standard container runtime.

## Kubernetes pods

A pod represents a single instance of an app running in Kubernetes. The workloads that you run on Kubernetes are containerized apps. Unlike in a Docker environment, you can't run containers directly on Kubernetes. You package the container into a Kubernetes object called a pod. A pod is the smallest object that you can create in Kubernetes.

<figure><img src="../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

A single pod can hold a group of one or more containers. However, a pod typically doesn't contain multiples of the same app.

A pod includes information about the shared storage and network configuration and a specification about how to run its packaged containers. You use pod templates to define the information about the pods that run in your cluster. Pod templates are YAML-coded files that you reuse and include in other objects to manage pod deployments.

<figure><img src="../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>

## Lifecycle of a Kubernetes pod <a href="#lifecycle-of-a-kubernetes-pod" id="lifecycle-of-a-kubernetes-pod"></a>

Kubernetes pods have a distinct lifecycle that affects the way you deploy, run, and update pods. You start by submitting the pod YAML manifest to the cluster. After the manifest file is submitted and persisted to the cluster, it defines the desired state of the pod. The scheduler schedules the pod to a healthy node that has enough resources to run the pod.

<figure><img src="../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

## Deploy a container instance in Azure using the Azure portal <a href="#quickstart-deploy-a-container-instance-in-azure-using-the-azure-portal" id="quickstart-deploy-a-container-instance-in-azure-using-the-azure-portal"></a>

Use Azure Container Instances to run serverless Docker containers in Azure with simplicity and speed. Deploy an application to a container instance on-demand when you don't need a full container orchestration platform like Azure Kubernetes Service.

In this quickstart, you use the Azure portal to deploy an isolated Docker container and make its application available with a fully qualified domain name (FQDN). After configuring a few settings and deploying the container, you can browse to the running application:

Steps:

* Sign in to the [Azure portal](https://portal.azure.com/).
* Create a container instance

<figure><img src="../.gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>

* Select Containers > Container Instances.

<figure><img src="../.gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>

On the **Basics** page, choose a subscription and enter the following values for **Resource group**, **Container name**, **Image source**, and **Container image**.

* Resource group: **Create new** > `myresourcegroup`
* Container name: `mycontainer`
* Image source: **Quickstart images**
* Container image: `mcr.microsoft.com/azuredocs/aci-helloworld:latest` (Linux)

<figure><img src="../.gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure>

Leave the other values as their defaults, then select **Next: Networking**.

On the **Networking** page, specify a **DNS name label** for your container. The name must be unique within the Azure region where you create the container instance. Your container will be publicly reachable at `<dns-name-label>.<region>.azurecontainer.io`. If you receive a "DNS name label not available" error message, try a different DNS name label.

An auto-generated hash is added as a DNS name label to your container instance's fully qualified domain name (FQDN), which prevents malicious subdomain takeover. Specify the **DNS name label scope reuse** for the FQDN. You can choose one of these options:

* Tenant
* Subscription
* Resource Group
* No reuse
* Any reuse (This option is the least secure.)

For this example, select **Tenant**.

<figure><img src="../.gitbook/assets/image (11) (1).png" alt=""><figcaption></figcaption></figure>

Leave all other settings as their defaults, then select **Review + create**.

When the validation completes, you're shown a summary of the container's settings. Select **Create** to submit your container deployment request.

<figure><img src="../.gitbook/assets/image (12) (1).png" alt=""><figcaption></figcaption></figure>

Open the overview for the container group by navigating to **Resource Groups** > **myresourcegroup** > **mycontainer**. Make a note of the **FQDN** of the container instance and its **Status**.

\


<figure><img src="../.gitbook/assets/image (13) (1).png" alt=""><figcaption></figcaption></figure>

Once its **Status** is _Running_, navigate to the container's FQDN in your browser.

<figure><img src="../.gitbook/assets/image (14) (1).png" alt=""><figcaption></figcaption></figure>

### View container logs <a href="#view-container-logs" id="view-container-logs"></a>

Viewing the logs for a container instance is helpful when troubleshooting issues with your container or the application it runs.

To view the container's logs, under **Settings**, select **Containers** > **Logs**. You should see the HTTP GET request generated when you viewed the application in your browser.

<figure><img src="../.gitbook/assets/image (16) (1).png" alt=""><figcaption></figcaption></figure>

### Clean up resources <a href="#clean-up-resources" id="clean-up-resources"></a>

When you're done with the container, select **Overview** for the _mycontainer_ container instance, then select **Delete**.

<figure><img src="../.gitbook/assets/image (17) (1).png" alt=""><figcaption></figcaption></figure>
