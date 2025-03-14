# <span>Red Hat build of Keycloak</span> Quickstarts

_Red Hat build of Keycloak_ is an Open Source Identity and Access Management solution for modern Applications and Services.

The quickstarts herein provided demonstrate securing applications with _Red Hat build of Keycloak_ using different programming languages (and frameworks) 
and how to extend the server capabilities through a set of Java-based [Service Provider Interfaces(SPI)](https://access.redhat.com/documentation/en-us/red_hat_build_of_keycloak/24.0/html-single/server_developer_guide/index). 
They provide small, specific, working examples that can be used as a reference for your own project.

They are organized in this repository under different categories (or directories) as follows:

| Category  | Description                                                                           |
|-----------|---------------------------------------------------------------------------------------|
| extension | Examples about how to extend the server capabilities using some of the Keycloak SPIs. |
| jakarta   | Examples about how secure Jakarta Applications                                        |
| js        | Examples about how to secure JavaScript Applications                                  |
| nodejs    | Examples about how to secure NodeJS Applications                                      |
| spring    | Examples about how to secure Spring Applications                                      |

For any missing programming language and framework, you might want to consider looking at:

* **Quarkus**
  * [Securing a Client Application](https://quarkus.io/guides/security-oidc-code-flow-authentication-tutorial)
  * [Securing a Resource Server Application](https://quarkus.io/guides/security-oidc-bearer-token-authentication-tutorial)

We are happy to accept contributions for any reference that demonstrates how to
integrate _Red Hat build of Keycloak_ with additional programming languages or frameworks.

## Building, Testing, and Running the Quickstarts

First clone the quickstarts repository:

    git clone https://github.com/redhat-developer/rhbk-quickstarts.git
    cd rhbk-quickstarts

Each quickstart provides its own documentation with the steps you need to follow in order to build, test, and run the example.
Look at the `README.md` file at the root of a quickstart for more details.

## Maven repository

In order to use maven repository with the productized artifacts, it is needed to add repository https://maven.repository.redhat.com/ga/ to you settings.xml file.
You can see this repository in the [maven-settings.xml file](.github/maven-settings.xml). You can either add the repository to your default `settings.xml` file
,which is usually in `<your-home-dir>/.m2/settings.xml` file. Or you can run all the maven commands referred from individual quickstarts with the switch pointing to `maven-settings.xml` file:
```
mvn <other arguments as described in the specific quickstarts> -s <path to the file>/.github/maven-settings.xml
```

### Chrome driver version

Automated tests rely on the chrome browser present on your laptop. Also you need to have correct version of chrome driver according
to the version of the chrome browser used. In case of the issues, see [Chrome page](https://googlechromelabs.github.io/chrome-for-testing/) and download
correct chrome driver version for your Chrome browser. Then add system property `webdriver.chrome.driver` when running the tests according to chrome version
and add whole path to the chrome driver. For instance something like `-Dwebdriver.chrome.driver=/somedir/chromedriver-linux64-119.0.6045.105/chromedriver`.

### Product testing

Please refer to [README for product testing](README-product-testing.md).

## Help and Documentation

* [Documentation](https://www.keycloak.org/documentation.html)
* [User Mailing List](https://groups.google.com/d/forum/keycloak-user) - Mailing list for help and general questions about Keycloak

## Reporting Security Vulnerabilities

If you've found a security vulnerability, please look at the [instructions on how to properly report it](https://github.com/keycloak/keycloak/security/policy)

## Reporting an issue

If you believe you have discovered a defect in _Red Hat build of Keycloak_, please open [a JIRA issue](https://issues.redhat.com/browse/RHBK).
Please remember to provide a good summary, description as well as steps to reproduce the issue.

## Contributing

Before contributing to this repository, please read our [contributing guidelines](CONTRIBUTING.md).

## Related Projects

* [Keycloak](https://github.com/keycloak/keycloak) - Keycloak Server and Java adapters
* [Keycloak Node.js Connect](https://github.com/keycloak/keycloak-nodejs-connect) - Node.js adapter for Keycloak
* [Keycloak Node.js Admin Client](https://github.com/keycloak/keycloak-nodejs-admin-client) - Node.js library for Keycloak Admin REST API

## License

* [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0)

