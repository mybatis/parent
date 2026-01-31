MyBatis Parent
==============

[![Java CI](https://github.com/mybatis/parent/actions/workflows/ci.yaml/badge.svg)](https://github.com/mybatis/parent/actions/workflows/ci.yaml)
[![Maven Central](https://img.shields.io/maven-central/v/org.mybatis/mybatis-parent?label=Maven%20Central)](https://central.sonatype.com/artifact/org.mybatis/mybatis-parent)
[![License](https://img.shields.io/:license-apache-brightgreen.svg)](https://www.apache.org/licenses/LICENSE-2.0.html)

![mybatis](http://www.mybatis.org/images/mybatis-logo.png)

MyBatis-Parent is the MyBatis parent POM which has to be inherited by all MyBatis modules.

Building
========

- Builds require JDK 11 or better to build with and will continue to target JDK 8 runtimes.
- Allowable JDKs to build with include 11, 17, 21, or 22-ea
- Minimum maven version to build projects is 3.9.6
- Uses reproducable builds

Configurations
==============

- ```buildJdks``` - Uses ```<allowed.build.jdks>``` property for allowed jdks to build with.  Defaults to 17, 21, 22, 23-ea, or 24-ea.
- ```checkstyle``` - Uses ```<checkstyle.config>``` property for checkstyle configuration.
- ```clirr``` - Uses ```<clirr.comparisonVersion>``` property version to compare prior releases against.
- ```formatter``` - Uses ```<formatter.config>``` property for formatting configuration.  Default spacing is 2 character spacing.
- ```htmlJavadocs``` - Uses ```<html.javadocType>``` property for html type for javadocs.  Default to -html5.
- ```importsOrder``` - Uses ```<impsortGroups>``` property for import sort order.  Defaults to au,ch,com,config,de,examples,io,jakarta,java,javassist,javax,lombok,mockit,net,nl,ognl,org.
- ```JPMS``` - Uses ```<module.name>``` property required to override in every downstream module for automatic modular name.
- ```spotbugs``` - Uses ```<spotbugs.onlyAnalyze>``` property to control spotbugs analyzation.  Defaults to not set.

- ```compiler``` - Controlled through ```<java.version>``` and ```<java.release.version>``` setting source, target, and release with possibilty for split tests.
- ```encoding``` - Uses UTF-8 by default which can be overridden through ```<project.build.sourceEncoding>```, ```<project.build.resourceEncoding>```, and ```<project.reporting.outputEncoding>```.
- ```reproducable``` - Set ```<project.build.outputTimestamp>``` to controll reproducable build timestamp, this will auto update during releases; if not overridden, it will use value from last parent release.

Depedencies
===========

- Asm 9.7
- Mybatis Base Bundle 11
- Bnd 7.0.0
- Build Tools 1.3.1
- Checkstyle 10.17.0
- Extra Enforcer Rules 1.8.0
- Fluido 2.0.0-M9
- License 4.5

Plugins
=======

- Antrun 3.1.0
- Assembly 3.7.1
- Bnd 7.0.0
- Checkstyle 3.4.0
- Clean 3.3.2
- Clirr 2.8
- Compiler 3.13.0
- Coveralls 4.5.0-M3
- Dependency 3.7.1
- Deploy 3.1.2
- Enforcer 3.5.0
- Formatter 2.24.1
- Git Commit 9.0.1
- Gpgp 3.2.4
- Impsort 1.11.0
- Install 3.1.2
- Jacoco 0.8.12
- Jar 3.4.2
- Javadoc 3.8.0
- Jxr 3.4.0
- License 4.5
- Lifecycle 1.0.0
- Modernizer 2.9.0
- Pdf 1.6.1
- Pmd 3.24.0
- Project Info Reports 3.6.2
- Release 3.1.1
- Resources 3.3.1
- Rewrite 5.37.1
- Scm Publish 3.3.0
- Shade 3.6.0
- Site 4.0.0-M16
- Sonar 4.0.0.4121
- Sortpom 4.0.0
- Source 3.3.1
- Spotbugs 4.8.6.0
- Surefire 3.3.1
- Taglist 3.1.0
- Versions 2.17.1
- Whitespace 1.3.2

OSGI
====
- ```<osgi.symbolicName>``` as ```${project.groupId}.${project.artifactId}```
- ```<osgi.export>``` as ```${project.groupId}.*;version=${project.version};-noimport:=true```
- ```<osgi.import>``` as ```*```
- ```<osgi.dynamicImport>``` as ```empty```
- ```<osgi.private>``` as ```empty```

Tests
=====
- ```<excludedGroups>``` add slow test groups here and annotate classes similar to ```@Tag('groupName')``` whcih will auto enable on CI only

Site
====
- ```<topSiteURL>``` is set back upon itself as a hack to fix defect in maven site for single module builds to avoid maven detecting as 'projectname.git' and placing one folder up from staging.  Set this to empty for multi module builds.

See more details in [pom](pom.xml)
