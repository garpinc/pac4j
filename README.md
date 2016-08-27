<p align="center">
  <img src="https://pac4j.github.io/pac4j/img/logo.png" width="300" />
</p>

`pac4j` is an **easy** and **powerful security engine** for **Java** to authenticate users, get their profiles and manage authorizations in order to secure web applications. It provides a comprehensive set of **concepts and components**. It is based on Java 8 and available under the Apache 2 license.

It is **available for most frameworks / tools** and **supports most authentication / authorization mechanisms**.

## Authentication mechanims:

[OAuth (Facebook, Twitter, Google...)](https://github.com/pac4j/pac4j/wiki/Other-clients) - [SAML](https://github.com/pac4j/pac4j/wiki/SAML-protocol) - [CAS](https://github.com/pac4j/pac4j/wiki/CAS-protocol) - [OpenID Connect](https://github.com/pac4j/pac4j/wiki/OpenID-Connect-protocol) - [HTTP](https://github.com/pac4j/pac4j/wiki/Other-clients) - [OpenID](https://github.com/pac4j/pac4j/wiki/Other-clients) - [Google App Engine](https://github.com/pac4j/pac4j/wiki/Other-clients)

[LDAP](https://github.com/pac4j/pac4j/wiki/Authenticators) - [SQL](https://github.com/pac4j/pac4j/wiki/Authenticators) - [JWT](https://github.com/pac4j/pac4j/wiki/Authenticators) - [MongoDB](https://github.com/pac4j/pac4j/wiki/Authenticators) - [Stormpath](https://github.com/pac4j/pac4j/wiki/Authenticators)


## Authorization mechanims:

[Roles / permissions](https://github.com/pac4j/pac4j/wiki/Authorizers) - [Anonymous / remember-me / (fully) authenticated](https://github.com/pac4j/pac4j/wiki/Authorizers)

[CORS](https://github.com/pac4j/pac4j/wiki/Authorizers) - [CSRF](https://github.com/pac4j/pac4j/wiki/Authorizers) - [IP address](https://github.com/pac4j/pac4j/wiki/Authorizers) - [HTTP Security headers](https://github.com/pac4j/pac4j/wiki/Authorizers)


## Available implementations (*click on your framework*):

[J2E](https://github.com/pac4j/j2e-pac4j) - [Spring Boot](https://github.com/pac4j/spring-webmvc-pac4j) - [Spring Web MVC](https://github.com/pac4j/spring-webmvc-pac4j) - [Spring Security](https://github.com/pac4j/spring-security-pac4j) - [Apache Shiro](https://github.com/bujiio/buji-pac4j)

[Play 2 framework](https://github.com/pac4j/play-pac4j) - [Vertx](https://github.com/pac4j/vertx-pac4j) - [Spark Java framework](https://github.com/pac4j/spark-pac4j) - [Ratpack](http://ratpack.io/manual/current/pac4j.html#pac4j) - [Undertow](https://github.com/pac4j/undertow-pac4j)

[SSO CAS server](https://apereo.github.io/cas/4.2.x/integration/Delegate-Authentication.html) - [Dropwizard](https://github.com/evnm/dropwizard-pac4j) - [Knox gateway for Hadoop](http://knox.apache.org/books/knox-0-9-0/user-guide.html#Pac4j+Provider+-+CAS+/+OAuth+/+SAML+/+OpenID+Connect) - [Jooby framework](http://jooby.org/doc/pac4j)

---

## Main concepts and components:

1) A [**client**](https://github.com/pac4j/pac4j/wiki/Clients) represents an authentication mechanism. It performs the login process and returns a user profile. An indirect client is for UI authentication while a direct client is for web services authentication

2) An [**authorizer**](https://github.com/pac4j/pac4j/wiki/Authorizers) is meant to check authorizations on the authenticated user profile(s) or on the current web context

3) A [**matcher**](https://github.com/pac4j/pac4j/wiki/Matchers) defines whether the security must apply on a specific url

4) A [**config**](https://github.com/pac4j/pac4j/blob/master/pac4j-core/src/main/java/org/pac4j/core/config/Config.java) defines the security configuration via clients, authorizers and matchers

5) The ["**security filter**"](https://github.com/pac4j/pac4j/blob/master/pac4j-core/src/main/java/org/pac4j/core/engine/DefaultSecurityLogic.java) (or whatever the mechanism used to intercept HTTP requests) protects an url by checking that the user is authenticated and that the authorizations are valid, according to the clients and authorizers configuration. If the user is not authenticated, it performs authentication for direct clients or starts the login process for indirect clients

6) The ["**callback controller**"](https://github.com/pac4j/pac4j/blob/master/pac4j-core/src/main/java/org/pac4j/core/engine/DefaultCallbackLogic.java) finishes the login process for an indirect client

7) The [**application logout controller**"](https://github.com/pac4j/pac4j/blob/master/pac4j-core/src/main/java/org/pac4j/core/engine/DefaultApplicationLogoutLogic.java) logs out the user from the application.


## Versions

The version **1.9.2-SNAPSHOT** is under development. Maven artifacts are built via Travis: [![Build Status](https://travis-ci.org/pac4j/pac4j.png?branch=master)](https://travis-ci.org/pac4j/pac4j) and available in the [Sonatype snapshots repository](https://oss.sonatype.org/content/repositories/snapshots/org/pac4j).

The source code can be cloned and locally built via Maven:

```shell
git clone git@github.com:pac4j/pac4j.git
cd pac4j
mvn clean install
```

The latest released version is the [![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.pac4j/pac4j/badge.svg?style=flat)](https://maven-badges.herokuapp.com/maven-central/org.pac4j/pac4j), available in the [Maven central repository](http://search.maven.org/#search%7Cga%7C1%7Cpac4j-). See the [release notes](https://github.com/pac4j/pac4j/wiki/Versions).

Read the [documentation](https://github.com/pac4j/pac4j/wiki) for more information.


## Need help?

If you have any question, please use the following mailing lists:
- [pac4j users](https://groups.google.com/forum/?hl=en#!forum/pac4j-users)
- [pac4j developers](https://groups.google.com/forum/?hl=en#!forum/pac4j-dev)
