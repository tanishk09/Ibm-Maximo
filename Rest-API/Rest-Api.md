### Rest API 

### Documenation
https://www.ibm.com/docs/en/mam/7.6.0?topic=applications-rest-api

### Bruno
https://bportaluri.com/2012/02/maximo-rest-apis-reference-material.html

The Representational State Transfer (REST) application programming interface (API) provides a way for external applications to query and update application data in Tivoli®'s process automation engine.

The REST API is part of the integration framework, and you can use it to integrate external applications with process automation engine applications. The REST API exposes business objects and integration object structures as REST resources. The REST API can provide resource data in either XML or JavaScript Object Notation (JSON) format. External applications can use the REST API to query and update application data.

REST API resources can be used without any configuration. The object structures that the REST API can query or update have a value of INTEGRATION in the Consumed By field in the Object Structures application.

The REST API supports create, query, update, and delete operations on resources by using standard HTTP GET, POST, PUT, and DELETE methods.

The REST API is part of the integration framework and handles requests from external consumers.

When an external consumer initiates a request, a REST API controller directs the resource request to the appropriate resource handler. The resource handler interacts with resources to execute the request. When the request is complete, the resulting resource or resource collection is processed by the resource serializer. The resource serializer returns the representation as the resource response. Serializers are provided for XML and JSON.

Because the REST API is within the integration framework, the REST API can use process automation engine authentication, authorization, and system properties.

The REST API controller is a servlet. Performance and tuning for load and scalability is done at the application server level as it is for other web components.

![image](https://github.com/user-attachments/assets/73624d78-b0ea-468b-9656-6e353fa925c2)

### Supported representations

The REST API supports XML and JSON as representations. Representations are supported by the implementation of serializer classes that are registered in system properties.

The XML and JSON representations are registered in the following REST API system properties:

- mxe.rest.serializer.mbo.xml
- mxe.rest.serializer.os.xml
- mxe.rest.serializer.mbo.json
- mxe.rest.serializer.os.json
  
You can extend serializers for custom processing. You can create serializers for existing resource types, and for individual instances of business object resources or object structure resources.

For object structure resources, the XML format for the REST API is similar to the format that is supported by the integration framework.

### Resource handlers and URIs

The REST API provides access to business objects and integration object structures. A handler class for each resource is registered in a system property.

The handler classes for the business object and object structure resources are registered in the mxe.rest.handler.mbo system property and the mxe.rest.handler.os system property.

You can extend handlers for custom processing. You can create handlers for other resource types, and for individual instances of business object resources or object structure resources.

REST API resources are addressed by using resource identifiers that are part of the Uniform Resource Identifier (URI). The URIs are used to address the entities that are represented as REST resources.

For example, the following URI accesses a collection of Person business objects. The mbo indicates the business object resource type and person is the resource:

***.../maxrest/rest/mbo/person***

For another example, the following URI accesses a collection of data for the Person object structure. The os indicates the object structure resource type and mxperson is the resource:

***.../maxrest/rest/os/mxperson***
