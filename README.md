# My Awesome Blog

Starter kit for the AHRI coding challenge, using .Net MVC, MSSQL Server and Docker.

# Get Started

The code challenge is to start building an awesome blog, with .Net MVC. 

Please provide a summary and a brief overview of what you have done to complete this code challenge.

# Docker

If you're using ``docker``, please ensure that your ``docker-compose`` is functional and ready for use. Check your ``Docker Desktop`` for more configuration settings.

## Running Docker Compose

1. Open the project solution in ``Visual Studio Community / Professional``.
1. Run the ``Docker Compose`` build.

Troubleshooting:
1. Switch to Windows containers, if haven't already.
1. If the ``docker-compose`` build fails via ``Visual Studio Community / Professional``, please ensure you have the following starter images:

```
docker pull microsoft/mssql-server-windows-developer
docker pull mcr.microsoft.com/dotnet/framework/aspnet:4.8-windowsservercore-ltsc2019
```

## Connecting to the MSSQL Server Docker Container via SSMS

After running the ``docker-compose`` build via ``Visual Studio Community / Professional``, run the ``docker inspect`` command below to get the ``server name``.

````bash
docker inspect -f "{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}" mssql
````

# Challenge

Develop and build a simple blog, with the following requirements:
1. Define user authentication
	- The authentication involves user and roles. For roles, just define ``author`` and ``administrator``. For example, Andy is an ``author`` and Adrian is an ``administrator``.
1. Authors are able to create a ``post`` and visitors are able to ``comment`` (freely, no authentication required to post comments). 
	- Administrators serve as moderators, CRUD operations are allowed on posts.
	- Authors are owners of their posts, CRUD operations required for posts.

Bonus:
API Service and Client: 
1. Define an Web API service in .Net MVC, for requesting the blog posts (with any form of API authentication), to allow other clients to perform CRUD operations.
1. Using React, build an API client to your awesome blog, able to:
    - Perform CRUD operations on posts, for authors.
	- To retrieve posts for visitors.

Optional:
- Using Docker for local development, please feel free to modify provided docker files to suit your development needs.
- Connecting to a database server, for blog database schema and structure.