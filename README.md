# Ballerina SCIM Connector

*The system for Cross-domain Identity Management (SCIM) specification
 is designed to make managing user identities in cloud-based applications 
 and services easier.*

### Why do you need SCIM

The SCIM protocol is an application-level HTTP-based protocol for provisioning and managing 
identity data on the web and in cross-domain environments such as enterprise-to-cloud 
service providers or inter-cloud scenarios.  The protocol provides RESTful APIs for easier
creation, modification, retrieval, and discovery of core identity resources such as Users
and Groups, as well as custom resources and resource extensions. 

### Why would you use a Ballerina connector for SCIM

Ballerina makes integration with data sources, services, or network-connect APIs much easier than
ever before. Ballerina can be used to easily integrate the SCIM REST API with other endpoints.
The SCIM connector enables you to access the SCIM REST API through Ballerina. The actions of the
SCIM connector are invoked using a Ballerina main function. 

WSO2 Identity Server uses SCIM for identity provisioning and therefore you can deploay the wso2 
Identity Server and use it to run the samples. 


The following sections provide you with information on how to use the Ballerina SCIM connector.

## Compatibility
| Language Version        | Connector Version          | API Versions  |
| ------------- |:-------------:| -----:|
| ballerina-0.970.0-beta1-SNAPSHOT     | 0.9.3 | SCIM2.0 |


## Getting started

1. Clone and build Ballerina from the source by following the steps given in the README.md 
file at https://github.com/ballerina-lang/ballerina
2. Extract the Ballerina distribution created at
 `distribution/zip/ballerina/target/ballerina-<version>-SNAPSHOT.zip` and set the 
 PATH environment variable to the bin directory.

## Working with SCIM connector actions

In order for you to use the SCIM connector, first you need to create a ScimConnector 
endpoint.

```ballerina
endpoint Client scimEP {
    baseUrl:"https://localhost:9443",
    clientConfig:{
                     auth:{
                              scheme:"oauth",
                              accessToken:"<......>",
                              clientId:"<......>",
                              clientSecret:"<......>",
                              refreshToken:"<......>",
                              refreshUrl:"<......>"
                          },
                     targets:[{url:"https://localhost:9443",
                                  secureSocket:{
                                                   trustStore:{
                                                                  filePath:"<......>",
                                                                  password:"<......>"
                                                              }
                                               }
                              }]
                 }
};
```