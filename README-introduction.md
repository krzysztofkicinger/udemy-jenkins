# Jenkins - Introduction

## What is Continuous Integration?

* Development practice
* Developers commit code to a shared repository on a regular basis
* Version Control System (shared repository) is being monitored - when a commit is detected, a build will be triggered automatically
* If the build is not green, developers will be notified immediately 

![Continuous Integration Picture](./docs/continuous_integration.png)

## Why do we need Continuous Integration?

* Detect problems or bugs, as early as possible, in the development cycle
* Since the entire code base is integrated, built and tested constantly, the potential bugs and errors are caught earlier in the life cycle which results in a better quality software

## Continuous Integration vs Delivery vs Deployment

**Continuous Integration** - the practice of merging development work with the main branch constantly

**Continuous Delivery** - continual delivery of code to an environment once the code is ready to ship. This could be staging or production. The idea is the product is delivered to a user base, which can be QAs or customers for review and inspection (unit tests during continuous integration cannot catch all the bugs in business logic, particularly design issues)

**Continuous Deployment** - the deployment or release of code to production as soon as it is ready. Continuous Deployment requires Continuous Delivery and Continuous Integration otherwise code quality would not be guaranteed.

## Continuous Integration as a Mindset

* Fixing broken builds should be treated as high priority issue for all team members
* Deployment process should be automated, no manual steps
* All team members should focus on delivering high-quality tests

## Jenkins Architecture

Jenkins uses a Master-Slave architecture to managed distributed builds.

**Master**

* Schedule build jobs
* Dispatch builds to the slaves for the actual job execution
* Monitor the slaves and record the build results
* Can also execute build jobs directly

**Slave**

* Small Java program that listens for requests from Jenkins` master
* Execute build jobs dispatched by the master

## Important Jenkins` terminology

**Job/Project**

* Terms used interchangeably
* Refer to runnable tasks that are controlled/monitored by Jenkins

**Slave/Node**

* **Slave** - computer that is set up to build projects for a master
* Jenkins runs a separate program called **slave agent** on slaves
* Slave registers to master and listens for requests from it
* **Node** - refers to all machines that are part of Jenkins grid, slaves and master

**Executor**

* Separate stream of builds to be run on a node in parallel
* Node can have one or more executors

**Build**

* Result of one of the projects

## Resources

* https://github.com/jenkinsci/docker/blob/master/README.md
