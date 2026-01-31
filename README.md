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

- Asm 9.9.1
- Base Bundle (mybatis) 13
- Bcel 6.12.0
- Bnd 7.2.1
- Build Tools (hazendaz) 1.5.0
- Caffeine 3.2.3
- Checkstyle 13.0.0
- Extra Enforcer Rules 1.11.0
- Fluido 2.1.0
- License 5.0.0

Plugins
=======

- Antrun 3.2.0
- Assembly 3.8.0
- Bnd 7.2.1
- Central Publishing 0.10.0
- Checkstyle 3.6.0
- Clean 3.5.0
- Clirr 2.8
- Compiler 3.14.1
- Coveralls 5.0.0
- Dependency 3.9.0
- Deploy 3.1.4
- Enforcer 3.6.2
- Formatter 2.29.0
- Git Commit 9.0.2
- Gpgp 3.2.8
- Impsort 1.13.0
- Install 3.1.4
- Jacoco 0.8.14
- Jar 3.5.0
- Javadoc 3.12.0
- Jxr 3.6.0
- License 5.0.0
- Lifecycle 1.0.0
- Modernizer 3.2.0
- Pmd 3.28.0
- Project Info Reports 3.9.0
- Release 3.3.1
- Resources 3.4.0
- Rewrite 6.28.0
- Scm Publish 3.3.0
- Shade 3.6.1
- Site 3.21.0
- Sonar 5.5.0.6356
- Sortpom 4.0.0
- Source 3.4.0
- Spotbugs 4.9.8.2
- Surefire 3.5.4
- Taglist 3.2.2
- Versions 2.21.0
- Whitespace 1.6.0

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
