# Resource Deployment Choice: Azure App Service vs Azure Virtual Machine

## Cost

For this Article CMS project, I chose Azure App Service. App Service reduces the amount of infrastructure that needs to be configured and maintained compared with deploying the application to an Azure Virtual Machine. For this relatively small Python/Flask application, a managed App Service is sufficient and avoids maintaining a dedicated VM operating system and web server.

## Scalability

Azure App Service provides built\-in options for scaling a web application by changing the App Service Plan or increasing the number of application instances. This is more convenient for a web application than manually configuring additional virtual machines and load balancing.

A Virtual Machine provides more control over compute resources, but scaling generally requires more infrastructure configuration and administration.

## Availability

Azure App Service manages much of the underlying web\-hosting infrastructure. This reduces the need to manage operating\-system maintenance and the web\-hosting environment directly.

With a Virtual Machine, I would be responsible for more of the availability configuration, such as VM maintenance, operating\-system updates, application processes, and potentially additional instances or load balancing.

## Workflow

App Service provided a simpler development and deployment workflow for this project. I connected the Article CMS GitHub repository to Azure App Service using GitHub Actions, allowing changes committed to the main branch to be built and deployed to the Azure\-hosted application.

Using a Virtual Machine would require additional steps such as configuring the VM, connecting through SSH, installing Python and application dependencies, configuring the web server, deploying the application, and maintaining the operating system.

## Final Choice

I chose **Azure App Service** because the Article CMS is a Python/Flask web application that does not require direct control over the underlying operating system. App Service provides a simpler deployment and maintenance experience while still supporting the Azure SQL Database, Azure Blob Storage, Microsoft Entra authentication, and GitHub deployment workflow used by the application.

The managed environment also allowed me to focus on implementing the CMS, storage integration, authentication, and logging rather than managing virtual\-machine infrastructure.

## What Could Change My Decision?

I would reconsider using App Service if a future version of the application required extensive operating\-system customization, specialized software that could not be supported by the App Service runtime, or direct control over networking and system\-level configuration.

For example, if the CMS needed custom background services, specialized system packages, or infrastructure that required administrator\-level access to the operating system, an Azure Virtual Machine could provide the additional control required. I would then evaluate whether the additional flexibility justified the extra deployment, security, patching, monitoring, and maintenance responsibilities.

