### Rest API 

### Documenation
https://www.ibm.com/docs/en/mam/7.6.0?topic=applications-rest-api

The Representational State Transfer (REST) application programming interface (API) provides a way for external applications to query and update application data in Tivoli®'s process automation engine.

The REST API is part of the integration framework, and you can use it to integrate external applications with process automation engine applications. The REST API exposes business objects and integration object structures as REST resources. The REST API can provide resource data in either XML or JavaScript Object Notation (JSON) format. External applications can use the REST API to query and update application data.

REST API resources can be used without any configuration. The object structures that the REST API can query or update have a value of INTEGRATION in the Consumed By field in the Object Structures application.

The REST API supports create, query, update, and delete operations on resources by using standard HTTP GET, POST, PUT, and DELETE methods.

The REST API is part of the integration framework and handles requests from external consumers.

When an external consumer initiates a request, a REST API controller directs the resource request to the appropriate resource handler. The resource handler interacts with resources to execute the request. When the request is complete, the resulting resource or resource collection is processed by the resource serializer. The resource serializer returns the representation as the resource response. Serializers are provided for XML and JSON.

Because the REST API is within the integration framework, the REST API can use process automation engine authentication, authorization, and system properties.

The REST API controller is a servlet. Performance and tuning for load and scalability is done at the application server level as it is for other web components.

![image](https://github.com/user-attachments/assets/73624d78-b0ea-468b-9656-6e353fa925c2)
