# Apigee Standard Policy

![alt text](https://github.com/pachouri/Architecture-and-System-Design/blob/main/diagram/Apigee_Standard_Policy.gif?raw=true)

- **Standard policies** are suitable for internal development and lightweight API solutions. Standard policies can be used with any [environment type](https://cloud.google.com/apigee/docs/api-platform/fundamentals/environments-overview#environment-types). To see the list of standard policies, see [Standard policies by category](https://cloud.google.com/apigee/docs/api-platform/reference/policies/reference-overview-policy#standard-policy-categories).
- **Extensible policies** provide more functionality than standard policies, including for traffic management, mediation, and security. The extensible policies also include policies to implement custom logic in the form of JavaScript, Python, Java, and XSLT stylesheets.

**Spike Arrest Policy** in Apigee is a powerful tool designed to protect your APIs from sudden and unexpected surges in traffic, often referred to as "spikes." These spikes can overwhelm your backend systems, leading to performance degradation, errors, and potential downtime.

**CORS (Cross-Origin Resource Sharing)** is a mechanism that allows web pages to make requests to servers on a different domain than the one from which the page originated. This is crucial for modern web applications that often rely on fetching data from external APIs or services.

**HTTP Modifier Policy** in Apigee is a powerful tool that allows you to modify HTTP headers and request/response bodies within your API flows. This flexibility enables you to customize the behavior of your APIs, enhance security, and address specific integration requirements.

**JSONtoXML Policy** in Apigee is a powerful tool that allows you to seamlessly convert JSON data into XML format within your API flows. This is particularly useful when integrating with systems that require XML-formatted data or when dealing with legacy APIs that only accept XML.

**OAS Validation Policy** in Apigee is a powerful tool that ensures your API conforms to the OpenAPI Specification (OAS). This specification provides a standardized way to describe RESTful APIs, making them easier to understand, document, and consume.

**PublishMessage Policy** in Apigee is a powerful tool that enables you to send messages to a message broker or queueing system. This is essential for building asynchronous communication patterns and integrating with other systems that rely on messaging.

**RaiseFault Policy** in Apigee is a powerful tool that allows you to explicitly raise faults within your API flows. Faults are error conditions that can be triggered under certain circumstances, such as invalid input, unexpected errors, or business logic failures.

**ReadPropertySet Policy** in Apigee is a powerful tool that allows you to read and access properties stored in the Apigee property set. Property sets are key-value pairs that can be used to store configuration data, custom variables, or other information that you want to use within your API flows.

**SOAPMessageValidation Policy** in Apigee is a powerful tool that allows you to validate incoming SOAP messages against a predefined schema. This ensures that the messages adhere to the expected structure and data types, preventing errors and improving the reliability of your API.

**XMLtoJSON Policy** in Apigee is a powerful tool that allows you to seamlessly convert XML data into JSON format within your API flows. This is particularly useful when integrating with systems that require JSON-formatted data or when dealing with legacy APIs that only accept XML.

**AccessControl Policy** in Apigee is a powerful tool that enables you to enforce access control rules within your API flows. This is crucial for ensuring that only authorized users or applications can access your API's resources.

**HMAC Policy** in Apigee is a powerful tool that allows you to implement HMAC (Hash-based Message Authentication Code) authentication for your APIs. HMAC is a cryptographic algorithm that provides message integrity and authentication, ensuring that data has not been tampered with and that it originates from a trusted source.

JWT (JSON Web Token) Policies in Apigee are powerful tools that allow you to validate, decode, and utilize JWTs within your API flows. JWTs are a standard method for securely transmitting information between parties. They are often used for authentication, authorization, and data exchange.

**VerifyIAM Policies** in Apigee are powerful tools that allow you to verify the identity and access permissions of users or applications before granting them access to your API resources. These policies are crucial for implementing robust security and authorization mechanisms within your API flows.

**AssertCondition Policy** in Apigee is a powerful tool that allows you to assert conditions within your API flows. This is useful for validating input, checking for specific conditions, or controlling the flow of your API based on certain criteria.

**ExternalCallout Policy** in Apigee is a powerful tool that allows you to invoke external services or APIs from within your API flows. This enables you to integrate with third-party systems, leverage external functionalities, or build composite APIs.
