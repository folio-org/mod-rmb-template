# MOD-FOLIO

Copyright (C) 2017 The Open Library Foundation

This software is distributed under the terms of the Apache License, Version 2.0. See the file "LICENSE" for more information.

## Introduction

This is the repository for the Maven archetype used to generate an RMB-based-backend module.

RAML Module Builder (or RMB for short) is a VertX-based toolkit that allows you to:
* synthesize API endpoints (via a Java interface) based on a RAML document; and
* synthesize POJOs based on declared JSON schema definitions.

For additional information on RMB, please refer to the [RAML Module Builder README](https://github.com/folio-org/raml-module-builder).


## Usage

To use the archetype, first, install it locally. 

```
mvn clean install
```

On success, go to the root that will host your new project folder and run the following command.

```
mvn archetype:generate              	\
  -DarchetypeGroupId=org.folio        \
  -DarchetypeArtifactId=mod-folio     \
  -DarchetypeVersion=1.0-SNAPSHOT     \
  -DgroupId=org.folio                 \
  -DartifactId={project-module-name-here}
```

> NOTE: The new project will includes a .gitignore file that include paths which RMB uses to auto-generate code in. Since the Java files generated in these folders are rebuilt every single time, the paths are not under source control.

`cd` into the new project's directory.

 

Next, add the new project to source control. Add the `raml-util` module afterwards. 

```
git init
git submodule add https://github.com/folio-org/raml ramls/raml-util
```

[raml-util](https://github.com/folio-org/raml) exposes traits shared by various RMB-based FOLIO modules.

At this point, the new module is ready for compilation.

`mvn clean install`
