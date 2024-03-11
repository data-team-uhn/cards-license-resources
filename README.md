# CARDS (Clinical Archive for Data Science) - License Resources

This repository contains resource files needed for bundling LICENSE and NOTICE files inside the CARDS built artifacts.

This must be kept separate from the main CARDS repository since it cannot both be built and be used as a build depencency at the same time.

It works as a Maven Remote Resources bundle.
The `maven-remote-resources-plugin` is used to build this module as a remote resources bundle,
listing the two source files as remote resources.
Then, when building the other CARDS modules,
it is used to generate resources that are included in the resulting artifact.
The LICENSE file is copied as is,
but the NOTICE file is interpreted as a Velocity script,
with information about the project available as scripting variables.

The LICENSE file is the standard Apache 2.0 license text.

The NOTICE file will generate some short information about the artifact itself (name, copyright, license),
and list all the used dependencies along with their respective licenses.

## Prerequisites:
* Java 11
* Maven 3.3+

## Build:
`mvn clean install`
