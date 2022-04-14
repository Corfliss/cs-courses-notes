---
Zettelkasten: 2022.04.12 13:37:06 +0700
---
# Review: Development Cycle
Basically, the development lifecycle wil require a requirements list. After that, it will be go to the analysis phase, then design phase, then code phase, then test phase, then review phase, then deploy phase, then to analysis phase again. But if I want to continue more about development process, it is sound something like this:
* Sequence of phase and activities to produce software artefacts (i.e. source code, assets, configuration) from given requirements
* The essence of most development processes is how to transform given requirements to a software product.

In addition, software engineering will only cover about the requirements, analysis, and design of it. Advanced programming will discuss about design, code, test, review, and deployment part.
* Code and test is about continuous integration (CI)
* Review and deploy is about continuous delivery/deployment (CD)

# Provisioning and Deployment
## Definition
* Provisioning prepares the environment (e.g infrastructure, system and software dependencies, security, etc.)
* Deployment puts the software artefacts into the provisioned environment and makes them operational
## Example
* Deploying Python web app
	* Setup virtual machine
	* Install git, Pythoon, reverse proxy (e.g. nginx)
	* Get source code of the application (which means is common in Python-based app)
		* If you are using language that involves compilation (e.g Java) then you need to get the runnable executable (e.g JAR file)
	* Configure reverse proxy to direct requests to the app server 

## Deployment Challenges
### Tenancy
* Scaling and managing app
* Will be challenging if there are more than 1 hosts for the app.

### Dependency
* App can have different dependencies
* Example,  An app requires Python to 3.5 due to certain library.

### Environemnt Parity
* What is work on one machine might not work on the other

### Vertical Scaling
* The app mst be shut down if we want to upsize/downsize the environment

### Horizontal Scaling
* Prone to error if done manually

### Etc.

# Container Technology
## Virtualization
* Hardware virtualization
	* E.g. VirtualBox, Hyper-V, IaaS offering on cloud provider
* Provides abstraction layer on top of physical computing resources
	* E.g. CPU, GPU, memory, network, disks
* Allows running >= 1 virtual computer (or machine) on a host
* Each VM specs can be customized
* 
## OS-level Virtualization
* OS is also responsible for allocating resources for the processes
* You can learn more on [[Operating System]]
* Container creates an isolated execution environment of one or more processes on a host OS
* If required, containers can interact with each other via network or shared filesystem.
### For Container
* The container technology provides abstraction layer on top of resources and OS features
	* Low-level: libcontainer, lxc, jail, chroot
	* High-level: Docker, podman, rkt
* Each container may have isolated view of the filesystem and computing resources of the host OS

## Docker
* Arguably one of the earliest pioneer that makes container technology more accessible to app developers
* Provides Docker daemon that runs on a host and a client (i.e.. docker CLI that interfaces with it)
### Example of Python Web App as Container
* See the Dockerfile at Flaskr Tutorial
* Putting and running a Flask app as container
* The demo only shows how to bundle the app into a container image

Reference:
Provisioning & Deployment: From Traditional to Container slide from Daya Adianto