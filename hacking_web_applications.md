# Hacking Web Applications

## Web applications concepts

Web applications provide an interface between end users and web servers.
They are vulnerable to various attacks such as SQL injection, cross-site scripting, and session hijacking.

![Web applications working](img/web_applications_working.png "Web applications working")

### Architecture

Web applications run on web browsers and use a set of server-side scripts to execute the application.

The architecture includes different devices, web browsers, and external web services.
It consists of three layers:

1. client or presentation layer
2. business logic layer
3. database layer

#### Client or presentation layer

It includes all physical devices present on the client side.

#### Business logic layer

It consists of two layers:

- the **web server logic layer** contains various components (firewall, an HTTP request parser, a proxy caching server, an authentication and login handler, a resource handler, and a hardware component, e.g., a server)
- the **business logic layer** includes the functional logic of the web application, implemented with .NET, Java, and "middleware".

#### Database layer

It consists of cloud services, a B2B layer that holds all the commercial transactions, and a database server that supplies an organization's production data in a structured form.

![Web application architecture](img/web_application_architecture.png "Web application architecture")

### Web services

W.S. is an application or software that is deployed over the internet.
It uses a standard messaging protocol to enable communication between applications developed on different platform.

#### Architecture

Service providers offer web services. They deploy and publish service descriptions of a web service to a service registry.

Three roles:

- provider
- requester (the browser is a requester)
- registry

Three operations:

- publish
- find
- bind

Two artifacts:

- service
- service description

![Web service architecture](img/web_service_architecture.png "Web service architecture")

#### Characteristics of Web service

- XML-based
- coarse-grained service
- loosely coupled
- asynchronous and synchronous support
- RPC support

#### Type of

- SOAP (Simple Object Access Protocol) define the XML format
- RESTful (REpresentational State Transfer) are designed to make the services more productive

#### Components of

- UDDI (Universal Description, Discovery, and Integration) is a directory service that lists all the services available
- WSDL (Web Services Description Language) is an XML-based language that describes and traces web services
- WS-Security (Web Services Security) plays an important role in securing web services. It is an extension of SOAP

### Vulnerability stack

It shows various layers and the corresponding elements / mechanisms / services that make web applications vulnerable.

![Vulnerability stack](img/vulnerability_stack.png "Vulnerability stack")

Attackers exploit the vulnerabilities of one or more elements among the seven levels to gain unrestricted access to an application or the entire network.

## Web applications threats

## Web application hacking methodology

## Web API, Webhooks and Web Shell

## Web application security

