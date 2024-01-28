MyBatis Parent
==============

[![Java CI](https://github.com/mybatis/parent/actions/workflows/ci.yaml/badge.svg)](https://github.com/mybatis/parent/actions/workflows/ci.yaml)
[![Maven central](https://maven-badges.herokuapp.com/maven-central/org.mybatis/mybatis-parent/badge.svg)](https://maven-badges.herokuapp.com/maven-central/org.mybatis/mybatis-parent)
[![Sonatype Nexus (Snapshots)](https://img.shields.io/nexus/s/https/oss.sonatype.org/org.mybatis/mybatis-parent.svg)](https://oss.sonatype.org/content/repositories/snapshots/org/mybatis/mybatis-parent/)
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

- ```buildJdks``` - Uses ```<allowed.build.jdks>``` property for allowed jdks to build with.  Defaults to 11, 17, 21, or 22-ea.
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

- Asm 9.6
- Mybatis Base Bundle 11
- Bnd 7.0.0
- Build Tools 1.3.1
- Checkstyle 10.13.0
- Extra Enforcer Rules 1.7.0
- Fluido 2.0.0-M8
- License 4.3

Plugins
=======

- Antrun 3.1.0
- Assembly 3.6.0
- Bnd 7.0.0
- Checkstyle 3.3.1
- Clean 3.3.2
- Clirr 2.8
- Compiler 3.12.1
- Coveralls 4.5.0-M3
- Dependency 3.6.1
- Deploy 3.1.1
- Enforcer 3.4.1
- Formatter 2.23.0
- Git Commit 7.0.0
- Gpgp 3.1.0
- Impsort 1.9.0
- Install 3.1.1
- Jacoco 0.8.11
- Jar 3.3.0
- Javadoc 3.6.3
- Jxr 3.3.2
- License 4.3
- Lifecycle 1.0.0
- Modernizer 2.7.0
- Pdf 1.6.1
- Pmd 3.21.2
- Project Info Reports 3.5.0
- Release 3.0.1
- Resources 3.3.1
- Rewrite 5.21.0
- Scm Publish 3.2.1
- Shade 3.5.1
- Site 4.0.0-M13
- Sortpom 3.3.0
- Source 3.3.0
- Spotbugs 4.8.3.0
- Surefire 3.2.5
- Taglist 3.0.0
- Versions 2.16.2
- Whitespace 1.3.1

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
