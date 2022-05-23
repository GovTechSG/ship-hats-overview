# Nexus Repository

Nexus Repository provides artifact management across environments. 

Nexus Repository provides the following features:
- Ensures that your development, build, and production environments deploy consistent artifacts  
- Reduces errors due to differences in build artifacts
- Provides version control for your release artifacts to enable better control and easier rollback

**Topics**
- [Available Repository Flavours](#available-repository-flavours)
- [Nexus Proxy Repositories](#nexus-proxy-repositories)
- [Repository Types](#repository-types)
- [FAQs](#faqs)
- [Additional Resources](#additional-resources)

## Available Repository Flavours

Following reository flavours are available:

- Bower
- NPM
- Docker
- Nuget V2
- Pypi
- Rubygems
- Maven2
- Yum
- Raw

Each of these flavours can be further categorised as:
- Group
- Proxy
- Hosted


## Nexus Proxy Repositories

We have moved all the proxy repositories to S3-Proxy blobstore. So any new proxy repo request should select S3-Proxy as the blobstore.  All the other repo request (hosted/group) should move to S3Blobstore bucket. 

|S.No.|Proxy Type|Proxy Name|Proxy URL|Upstream URL (in this order)|
|---|---|---|---|---|  
1	|Bower|	bower-proxy|	https://nexus.ship.gov.sg/repository/bower-proxy/	|https://registry.bower.io
2	|NPM|	npm-proxy|	https://nexus.ship.gov.sg/repository/npm-proxy/|	https://registry.npmjs.org/
3|	Docker|	docker-proxy|	
https://nexus.ship.gov.sg/repository/docker-proxy/|https://registry-1.docker.io
4|	Nuget V2|	nuget-proxy|	https://nexus.ship.gov.sg/repository/nuget-proxy/	|https://www.nuget.org/api/v2/
5|	Pypi	|pypi-proxy|	https://nexus.ship.gov.sg/repository/pypi-proxy/	|https://pypi.org
6|	Rubygems|	rubygems-proxy|	https://nexus.ship.gov.sg/repository/rubygems-proxy/	|https://rubygems.org
7|	Maven2	|maven2-proxy	|https://nexus.ship.gov.sg/repository/maven2-proxy/	|https://repo.maven.apache.org/maven2
8|	Maven2|	maven2-bintray	|https://nexus.ship.gov.sg/repository/maven2-bintray/	|https://jcenter.bintray.com
9|	Maven2|	maven2-gradle	|https://nexus.ship.gov.sg/repository/maven2-gradle/	|https://plugins.gradle.org/m2/
10|	Maven2|	maven2-exetended-proxy|	https://nexus.ship.gov.sg/repository/maven2-extended-proxy/	|https://repo1.maven.org/maven2/ <br>https://jcenter.bintray.com <br>https://plugins.gradle.org/m2/
11|	Yum|	yum-proxy|	https://nexus.ship.gov.sg/repository/yum-proxy/	|http://mirror.centos.org/centos/
12|	Nuget V3|	nuget-sitecore-commerce	|https://nexus.ship.gov.sg/repository/nuget-sitecore-commerce/|	https://sitecore.myget.org/F/sc-commerce-packages/api/v3/index.json
13|	Nuget V3|	nuget-sitecore|	https://nexus.ship.gov.sg/repository/nuget-sitecore/|	https://sitecore.myget.org/F/sc-packages/api/v3/index.json
14|	Nuget V3|	nuget-api-proxy|	https://nexus.ship.gov.sg/repository/nuget-api-proxy/	|https://api.nuget.org/v3/index.json


## Repository Types

Following types of Repositories are available:
- [Proxy Repository](#proxy-repository)
- [Hosted Repository](#hosted-repository)
- [Group Repository](#group-repository)

### Proxy Repository
Proxy Repository is a repository linked to a remote repository. The Proxy Repository has a type `proxy`.  
Any request for a component is verified against the local content of the proxy repository. If no local component is found, the request is forwarded to the remote repository. The component is then retrieved and stored locally in the repository manager, which acts as a cache.  
Subsequent requests for the same component are then fulfilled from the local storage. This eliminates the network bandwidth and time overhead of retrieving the component from the remote repository again.

By default, the repository manager ships with the following configured proxy repositories:

- **maven-central:** Proxy repository accesses the Central Repository, formerly known as Maven Central.

- **[nuget.org](http://nuget.org/)-proxy:** This proxy repository accesses the [NuGet](https://www.nuget.org/) Gallery. It is the default component repository used by the nuget package management tool used for .Net development.

### Hosted Repository
A Hosted Repository is a repository that stores components in the repository manager as the authoritative location for these components. The Hosted Repository has a type `hosted`. 

By default, the repository manager ships with the following configured hosted repositories:

- **maven-releases:** This hosted repository uses the `maven2 repository format` with a release version policy. It is intended to be the repository where your organization publishes internal releases. You can also use this repository for third-party components that are not available in external repositories and can therefore not be retrieved via a configured proxy repository.

- **maven-snapshots:** This hosted repository uses the `maven2 repository format` with a snapshot version policy. It is intended to be the the repository where your organization publishes internal development versions, also known as snapshots.

- **nuget-hosted:** This hosted repository is intended to be the repository where your organization can publish internal releases in repository using the `NuGet repository format`.

### Group Repository  

Repository groups are a powerful feature of Nexus Repository Manager. They allow you to combine multiple repositories and other repository groups of the same repository format in a single repository group. This single group and the associated URL can then be used as a single access point to all components in a specific format sourced from a number of repositories.  

This eases the configuration for the users and at the same time allows the administrators to add more repositories and components without requiring changes on the client computers.  

>**Note:** The order of the repositories listed in *Ordered Group Repositories* is important. When the repository manager searches for a component in a group, it will return the first match. To reorder a repository in this list, click and then drag the repositories and groups in the *Ordered Group Repositories* selection list.  

The order of repositories or other groups in a group can be used to influence the effective metadata that will be retrieved from a repository group. 
**Best Practices**

- Place hosted repositories higher in the list than proxy repositories within the list. For proxy repositories, the repository manager needs to periodically check remote for updates, which will incur more overhead than a hosted repository lookup.  
- Place repositories with a higher probability of matching the majority of components higher in this list. If most of your components will be retrieved from the Central Repository, putting Central higher in this list than a smaller, more focused repository will improve the performance because the repository manager will not search the smaller remote repository for as many missing components.  


## FAQs

- [FAQs](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/tools-faq?id=sonatype-nexus-repository-faq)

## Additional Resources

- [Cleanup Policy for Nexus Repository](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/ship-hats-cleanup-policy-for-nexus-repository)
- [Nexus Repository Manager](https://www.sonatype.com/product-nexus-repository)