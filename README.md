# Sample Project - AEM Integrated SPA Editor 

This is a project template for AEM-based applications. It is intended as a best-practice set of examples as well as a potential starting point to develop your own functionality.


## Usage

To get started, create a new project with the [AEM Project Archetype](https://github.com/adobe/aem-project-archetype) using the *react frontend module*, using the following command line:

* Set `aemVersion=cloud` for [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html);  

* Set `sdkVersion=latest` for an [SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/aem-as-a-cloud-service-sdk.html) version is specified automicamente (e.g. `2024.8.17569.20240822T203847Z-240700`);  

* Set `frontendModule=react` for the react app.

```
mvn -B org.apache.maven.plugins:maven-archetype-plugin:3.2.1:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=50 \
 -D appTitle="aem-integrated-spa" \
 -D appId="aem-integrated-spa" \
 -D groupId="com.aem.integrated.spa" \
 -D aemVersion="cloud" \
 -D sdkVersion="latest" \
 -D includeDispatcherConfig="n" \
 -D frontendModule="react"  
```


## Modules

The main parts of the template are:

* [core:](core/README.md) Java bundle containing all core functionality like OSGi services, listeners or schedulers, as well as component-related Java code such as servlets or request filters.
* [ui.apps:](ui.apps/README.md) contains the /apps (and /etc) parts of the project, ie JS&CSS clientlibs, components, and templates
* [ui.content:](ui.content/README.md) contains sample content using the components from the ui.apps
* ui.config: contains runmode specific OSGi configs for the project
* [ui.frontend:](ui.frontend.general/README.md) an optional dedicated front-end build mechanism (Angular, React or general Webpack project)
* all: a single content package that embeds all of the compiled modules (bundles and content packages) including any vendor dependencies
* analyse: this module runs analysis on the project which provides additional validation for deploying into AEMaaCS

