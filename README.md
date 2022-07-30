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
- Allowable JDKs to build with include 11, 17, 18, 19-ea, or 20-ea
- Minimum maven version to build projects is 3.3.9
- Uses reproducable builds

Configurations
==============

- ```checkstyle``` - Uses ```<checkstyle.config>``` property which can be independently overridden as needed
- ```formatter``` - Uses ```<formatter.config>``` property which can be independently overridden as needed.  Default spacing is 2 character spacing.
- ```JPMS``` - Uses ```<module.name>``` property which needs overridden in every downstream module.
- ```encoding``` - Uses UTF-8 by default which can be overridden through ```<project.build.sourceEncoding>```, ```<project.build.resourceEncoding>```, and ```<project.reporting.outputEncoding>```.
- ```compiler``` - Controlled through ```<java.version>``` and ```<java.release.version>``` setting source, target, and release with possibilty for split tests.
- ```reproducable``` - Set ```<project.build.outputTimestamp``` to controll reproducable build timestamp, this will auto update during releases, it not overridden, it will use value from last parent release.

Depedencies
===========

- Asm 9.3
- Mybatis Base Bundle 9
- Bind api 2.3.3
- Bnd 6.3.1
- Build Tools 1.3.0
- Checkstyle 10.3.1
- Extra Enforcer Rules 1.6.1
- Fluido 1.11.1
- License 4.2.rc3
- Wagon Git 2.0.3
- Wagon 3.5.2

Plugins
=======

- Antrun 3.1.0
- Assembly 3.4.2
- Bundle 5.1.7
- Changes 2.12.1
- Checkstyle 3.1.2
- Clean 3.2.0
- Clirr 2.8
- Compiler 3.10.1
- Coveralls 4.4.1
- Dependency 3.3.0
- Deploy 3.0.0
- Enforcer 3.1.0
- Formatter 2.20.0
- Git Commit 5.0.0
- Gpgp 3.0.1
- Impsort 1.7.0
- Install 3.0.1
- Jacoco 0.8.8
- Jar 3.2.2
- Javadoc 3.4.0
- Jxr 3.2.0
- License 4.2.rc3
- Lifecycle 1.0.0
- Modernizer 2.4.0
- Pdf 1.6.0
- Pmd 3.17.0
- Project Info Reports 3.4.0
- Release 3.0.0-M6
- Resources 3.3.0
- Scm 1.12.2
- Shade 3.3.0
- Site 3.12.0
- Sortpom 3.2.0
- Source 3.2.1
- Spotbugs 4.7.1.1
- Surefire 3.0.0-M7
- Taglist 3.0.0
- Versions 2.11.0
- Whitespace 1.0.4

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

See more details in [pom](pom.xml)
