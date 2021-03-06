# OData Boot Services

The OData Boilerplate combines OpenUI5 with Spring Boot, OLingo and JPA and allows you to easily and quickly boot up a JVM based OData app based on modeling your data model in using JPA.

For convenience, a base-diagram for the JPA diagram editor has been provided as well. Once your data model is finished, the application with update the database schema of the connected database on first run. After every change and restart, the application will attempt to alter the database schema according to the changes detected in the JPA model.

By default, the application comes with just one entity: Members, that is automatically populated with a few names from Application.java

Once the application is running, you can browse to http://localhost:8080 to run the sample OpenUI5 application that is using the OData service. The service itself is available from http://localhost:8080/odata.svc

## Features (Deployee on any VM, including Tomcat, HANA Cloud Platform, Azure, But also on Plain java Using Build-in Tomcat)

- Deploys on any VM, including Tomcat, HANA Cloud Platform, Azure, but also on plain Java using built-in Tomcat
- Full CRUD support on all JPA entities
- Feature-complete OData v2 support, including $filter, $expand, $select, $count, $top, etc
- Language dependent annotation support for Smart controls (through i18n.properties files)
- Connects to most SQL databases, including SQL server, HANA, MySQL, HSQLDB, Derby
- Automatically creates database schema based on JPA model

## Prerequisites

To be able to run this application, you need Java JDK 1.7 (or higher) and Maven.

## Installation

To install the boilerplate, you can just clone this repository to your computer.

After cloning it, set the connection parameters to connect to a database in `application.properties`

## Usage

To run the application just enter `mvn spring-boot:run -P jar`

To stop the application press control-C

To build a jar run `mvn clean package`

To run the jar `mvn -jar target/odata-0.1.0.jar`

## HANA Cloud Platform

The boilerplate is compatible with both the local as well as the cloud-runtime of HANA cloud platform and will compile to a WAR when Maven profile 'hcp' is selected (which happens to be the default ;).

When the application is run on the HCP cloud, it will automatically connect to the default database connection and start updating the database schema there. It is of couse still possible to connect the Java application to another data-source using the cockpit.

When you run the application from Eclipse on a local HANA Cloud Platform runtime, the site will be available on http://localhost:8080/odata. Also, through configuration of web.xml, authentication is switched on. When you run the application on a local HCP runtime without modifying web.xml, you need to add a user to your local server. You can do this by double clicking your HCP local server and adding a user to the 'users' tab.
