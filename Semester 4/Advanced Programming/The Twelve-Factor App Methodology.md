---
Zettelkasten: 220322 131436 +0700
---
# Codebase
* One codebase tracked in revision control, many deploys
* One codebase comprises of artifacts of an app or a software module
* One codebase may have more than one deploy
# Dependencies
* Explitcitly declare and isolate dependencies
* Assume the operational environment does not have the required dependencies
# Config
* Store config in the environment
* Configs may vary across deploys/environments
* Configs should never be committed into VCS
# Backing Services
* Consumed over network during operation
* Allows swapping of the services dynamically
# Build, Release, Run
* Strictly separate build and run stages
# Dev/Prod Parity
* Keep development, staging, and production as similar as possible
* Make tech stack as similar as possible across environments
* Reduce "It works on my machine" mishaps
# Processes
* Applications should be deployed as one or more stateless processes with persisted data stored on a backing service.
# Port Binding
* Self-contained services should make themselves available to other services by specified ports.
# Concurrency
* Concurrency is advocated by scaling individual processes.
# Disposability
* Fast startup and shutdown are advocated for a more robust and resilient system.
# Logs
* Applications should produce logs as event streams and leave the execution environment to aggregate.
# Admin Processes
* Any needed admin tasks should be kept in source control and packaged with the application.

# Reference
https://12factor.net/
https://en.wikipedia.org/wiki/Twelve-Factor_App_methodology
CSUI Slides