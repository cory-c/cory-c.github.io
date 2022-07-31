---
title: Projects
toc: true
pannel_includes:
- toc
icon: fas fa-info-circle
order: 2
mermaid: true
---
# Contract First API Template

## API Generation
The template project enforces that the API is defined in the OpenAPI specification before code is implemented and ensures the contract is always up to date. Changing the exposed interface / contract requires updating the ServiceDefinition.yaml file first. At build time, the project reads from the ServiceDefinition.yaml file in the project root then generates request models, response models, interfaces and controller delegates for each endpoint in a single file called ControllerDelegates.cs. This file is not meant to be checked in, any changes in the ServiceDefinition.yaml are dynamically updated at build time.

## Development Process

### New API
[//]: # (graph LR)
[//]: # (A&#40;Write API <br>Contract&#41;)
[//]: # (--> B&#40;New Template <br>Project&#41;)
[//]: # (--> C&#40;Install Template <br>Project&#41;    )
[//]: # (--> D&#40;Copy Contract<br>into project&#41;)
[//]: # (--> E&#40;Build <br> Project&#41;)
[//]: # (--> |Delegates / Models <br>Generated| F&#40;Implement <br>Interfaces&#41;)
[//]: # (E --> |Contract<br> copied into<br>static SwaggerUI dist| F&#40;Implement <br>Interfaces&#41;)
[//]: # (--> G&#40;Run Application&#41;)
[![](https://mermaid.ink/img/pako:eNqNkU1LAzEQhv_KkFOEFu-LFPplWVApreJlLzGZbqPZJGRnKaXtf3fSD6vowZySeR-emSE7oYNBUYg6qbiGh0Xlgc9QviZLCMN5CXdvaTAOnpLSdHOK-_0BjOQTbuAZm-gUk5map_COP6CxLH1Lyrm_wYxd4Ykch7iFS68MWk8B4i_tVI4668zRBV-ya76foMOau7VwC4-8oGuP7Aw9Ji6bPdzLkgfCBj0do9ITppXS2J77TE-m79OADtGigTxVfvNmZDUsN6quMb2UYGxL_1Bn8UwuOg_DGJ3VbAn-lImeaDA1yhr-k10uVYLW7KpEwVej0kclKn9grouGV5kaSyGJYqVciz2hOgrLrdeioNThBZpYxf_bnKnDJxrKomc)](https://mermaid.live/edit#pako:eNqNkU1LAzEQhv_KkFOEFu-LFPplWVApreJlLzGZbqPZJGRnKaXtf3fSD6vowZySeR-emSE7oYNBUYg6qbiGh0Xlgc9QviZLCMN5CXdvaTAOnpLSdHOK-_0BjOQTbuAZm-gUk5map_COP6CxLH1Lyrm_wYxd4Ykch7iFS68MWk8B4i_tVI4668zRBV-ya76foMOau7VwC4-8oGuP7Aw9Ji6bPdzLkgfCBj0do9ITppXS2J77TE-m79OADtGigTxVfvNmZDUsN6quMb2UYGxL_1Bn8UwuOg_DGJ3VbAn-lImeaDA1yhr-k10uVYLW7KpEwVej0kclKn9grouGV5kaSyGJYqVciz2hOgrLrdeioNThBZpYxf_bnKnDJxrKomc)

### Updating an existing API

[//]: # (graph LR)
[//]: # (A&#40;Update API <br>Contract&#41;)
[//]: # (A --> B&#40;Build <br> Project&#41;)
[//]: # (B --> |Delegates / Models <br>Generated| C&#40;Implement Interfaces <br> or resolve build <br> errors&#41;)
[//]: # (B --> |Contract<br> copied into<br>static SwaggerUI dist| C&#40;Implement <br>Interfaces&#41;)
[//]: # (C --> D&#40;Run Application&#41;)
[![](https://mermaid.ink/img/pako:eNpVkctqwzAQRX9l0MqBhO5NCfhRiqGFkJCdN4o0cdTKkhmNW0qSf68iO4Ts5nG4d7hzFsprFLloHQB0JIcTfGxTA0W2H7RkhGLTwOuB1pV3TFLxYt7DarWGMitHY3UCYEP-CyMAE1Em4lKjxS4KBXiBz2hnQ6Lf0SHFsb5AlTX9YLFHx9A4RjpKhRMFnoAwePuDcHg4IZGnsHjyud-XAOUHgxqMY3_rA0s2Cna_suuQ9g1oE_jZ-IY9zGfpKknX2XZ0UAyDNSrqeDdtxVL0SL00OiZ4vo1awaeo1oo8llrSdxuTvUZuTFG-acOeRH6UNuBSyJH97s8pkTONeIdqI-Mj-pm6_gNmZ4j_)](https://mermaid.live/edit#pako:eNpVkctqwzAQRX9l0MqBhO5NCfhRiqGFkJCdN4o0cdTKkhmNW0qSf68iO4Ts5nG4d7hzFsprFLloHQB0JIcTfGxTA0W2H7RkhGLTwOuB1pV3TFLxYt7DarWGMitHY3UCYEP-CyMAE1Em4lKjxS4KBXiBz2hnQ6Lf0SHFsb5AlTX9YLFHx9A4RjpKhRMFnoAwePuDcHg4IZGnsHjyud-XAOUHgxqMY3_rA0s2Cna_suuQ9g1oE_jZ-IY9zGfpKknX2XZ0UAyDNSrqeDdtxVL0SL00OiZ4vo1awaeo1oo8llrSdxuTvUZuTFG-acOeRH6UNuBSyJH97s8pkTONeIdqI-Mj-pm6_gNmZ4j_)


## Installing the Template

The template can be used either by the dotnet CLI (dotnet new) or Visual Studio to create an new API project.
### General Info
https://docs.microsoft.com/en-us/dotnet/core/tools/custom-templates


### Installation
From the ContractFirst.Api directory run: the following command:
```
dotnet new --install ./
```
### Removing Template
```
dotnet new --uninstall cf-apils
```
### Create a project using template
```
dotnet new ContractFirst.WebApi
```

## Implementation

Once the ConrollerDelegates.cs file has been generated an implementation class needs to be provided and registered for each Interface. Take the following generated class, note the IPetController interface

```c#

public partial class PetController : Microsoft.AspNetCore.Mvc.ControllerBase
{
     private IPetController _implementation;

     public PetController(IPetController implementation)
     {
         _implementation = implementation;
     }

     // truncated ....

}
```
Add a new class that implements all the methods defined in the IPetController interface.

```c#
public class PetControllerImp : IPetConroller {

    // Implement methods in interface

}

```
Then register the new class in the Program.cs file

```c#
builder.Services.AddScoped<IPetController, PetControllerImp>();
```
## Swagger UI
Included in the API project is a local distrobution of [Swagger UI](https://github.com/swagger-api/swagger-ui) that is served as static content. On every build a copy of the ServiceDefinition.yaml is moved into the /wwwroot directory so any changes the the ServiceDefinition.yaml are reflected in the swagger page with running the application. The swagger page is availible at /swagger/index.html

## Configuration

## Management Endpoints

## Distributed Tracing

## Running Locally
Pre-Reqs, the following software needs to be installed: Java JDK, Docker, Git

#### Steps to run:

1. Build Project
2. Open terminal, cd into /Resources/Config directory
3. Run setup-config.sh, pass -l local file location of config or -r remote github repo

**Remote**

`./setup-config.sh -r https://github.com/cory-c/TestConfig.git`

**Local**

`./setup-config.sh -r https://github.com/cory-c/TestConfig.git`

Once config server is deployed and running, run the API project. The Swagger page will be availible at

https://localhost:7143/swagger/index.html



## Service Discovery
Coming soon

## Client Code Generation

## TODO
1. Get options monitor config working
2. Setup monitor admin endpoints. Update config / get config values
3. configure template / write instruction
4. Deploy to kubernetes
5. Service discovery (kubernetes)
6. Client Code generation
7. Endpoint to return config settings
8. Is config abstract for env? for implementation?
