

## Questions



*   Which deployment options do we currently use?
    *   Language-specific packaging format pattern
        *   Capistrano (Ironboard/Flatchat)
        *   edeliver (Phoeyonce)
    *   Service as a virtual machine pattern
        *   Forge (Ironbroker/Forge)
        *   AWS CodeDeploy (Registrar)
    *   Service as a container pattern
        *   IDE images (sort of)
        *   Deployer app (maybe? I have zero insight into that project)
    *   Serverless deployment pattern
        *   New ETL stuff
*   Do we have a preferred deployment option?
*   If we started a new project today what guidelines do we have for deployment?
*   What opportunities do we have for using _serverless_?


## Summary

Introduction



*   Deployment is a combination of two interrelated concepts: process and architecture
*   Key capabilities of  a production environment
    *   Service management interface — Enables developers to create, update, and configure services. Ideally, this interface is a REST API invoked by command-line and GUI deployment tools.
    *   Runtime service management — Attempts to ensure that the desired number of service instances is running at all times. If a service instance crashes or is somehow unable to handle requests, the production environment must restart it. If a machine crashes, the production environment must restart those service instances on a different machine.
    *   Monitoring — Provides developers with insight into what their services are doing, including log files and metrics. If there are problems, the production environment must alert the developers. Chapter 11 describes monitoring, also called observability.
    *   Request routing — Routes requests from users to the services.
*   There are 4 main deployment options: language-specific packages, virtual machines, containers, or serverless.

Deploying services using the Language-specific packaging format pattern



*   Benefits
    *   Fast deployment
    *   Efficient resource utilization, especially when running multiple instances on the same machine or within the same process
*   Drawbacks
    *   Lack of encapsulation of the technology stack
    *   No ability to constrain the resources consumed by a service instance
    *   Lack of isolation when running multiple service instances on the same machine
    *   Automatically determining where to place service instances is challenging

Deploying services using the Service as a virtual machine pattern



*   Benefits
    *   The VM image encapsulates the technology stack
    *   Isolated service instances
    *   Uses mature cloud infrastructure
*   Drawbacks
    *   Less-efficient resource utilization
    *   Relatively slow deployments
    *   System administration overhead

Deploying services using the Service as a container pattern



*   Benefits
    *   Encapsulation of the technology stack in which the API for managing your services becomes the container API
    *   Service instances are isolated
    *   Service instances's resources are constrained
*   Drawbacks
    *   Responsible for the undifferentiated heavy lifting of administering the container images
    *   You must patch the operating system and runtime
    *   You must administer the container infrastructure and possibly the VM infrastructure it runs on

Deploying services using the Serverless deployment pattern (AWS Lambda)



*   Benefits
    *   Integrated with many AWS services
    *   Eliminates many system administration tasks
    *   Elasticity
    *   Usage-based pricing
*   Drawbacks
    *   Long-tail latency
    *   Limited event/request-based programming model

Takeaways



*   You should choose the most lightweight deployment pattern that supports your service's requirements
*   When starting on your journey to microservices you'll probably deploy the services using the same mechanism you use for your monolithic application. You should only consider setting up a sophisticated deployment infrastructure such as Kubernetes once you've developed some services.
<p class='util--hide'>View <a href='https://learn.co/lessons/microservices-patterns-chapter-12'>Microservices Patterns Chapter 12</a> on Learn.co and start learning to code for free.</p>
