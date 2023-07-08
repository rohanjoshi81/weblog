---
title: "Ant + Ivy to Maven migration"
date: 2022-04-19T12:00:00+05:30
categories:
  - blog
tags:
  - guide
  - tech
---

This post is related to moving a apache ant and ivy based build automation and dependency management to maven. This could be helpful if you are working on a older Java project and want to move your project to spring boot and consequently work towards microservices.

# Steps 

- Add stage ivy:makepom to build_project target in build.xml , which will extract dependencies from ivy.xml as per pom standard.

- Add stage ivy:fixdeps to build_project target in build.xml , which will resolve the dependency versions.

- Check for missing dependencies in your pom and add dependency and version manually if any. Note for ivy dependency marked as latest.revision you will need to manually enter the latest version present in your artifact repository.

- Create a pom.xml with the dependencies and other required tags like properties with release and snaphot directory , repository with your artifact repository and scm with codebase path.

- Add required plugins in build tag with configurations as needed for project like compiler plugin , war plugin and release plugin.

That's all! You should be able to build your project using maven now.