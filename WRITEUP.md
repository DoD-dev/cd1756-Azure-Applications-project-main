# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app.

*For **both** a VM or App Service solution for the CMS app:*

- *Analyze costs, scalability, availability, and workflow*
    + Cost : VM cost is higher than App Service in both money and effort
    + Scalability : VM is less flexiable than App Service at small scale (auto scale hardware RAM, CPU) but VM can mutiply for larger scale
    + Availability : Microsoft manage underlaying hardware so App Service have high availability, VM solution provide high availability with group of VMs
    + Workflow : I need to manage config, install, deploy by myself in clude update OS, App Service do these things for me

- I choose App Service for deploying the app
    + Cost : App Service cost is lower than VM
    + Less effort needed to config App Service : App service support python v3.8, auto build and get dependiences and no need to 
    download and install runtime, sdk, other configurations, ... like VM
    + Auto deploy when connect to github (on VMs we need setup this pipeline)
    + Hardware limitation on App Service doesn't matter, 14GB of memory and 4 vCPU cores at maximum is more than enough 
    for this application.
    + App service give me full control with Azure Portal on web without ssh or remote access to the VM to start configuration
    + App Service scaling is more flexiable than VM scale set.

### Assess app changes that would change your decision.
I will consider switch to VM if my application expand in future
- If my app contains more microservices
- If my application written in language that App Service not support
- Some configurations App Service not support auto config
- High load under 1 instance
- Migrating some existing on-premise to cloud