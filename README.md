# MOD-FOLIO

Copyright (C) 2017 The Open Library Foundation

This software is distributed under the terms of the Apache License, Version 2.0. See the file "LICENSE" for more information.

## Introduction

This is the Maven archetype for an RMB-based-backend module for FOLIO.


For additional information on RMB, please refer to the [RAML Module Builder README](https://github.com/folio-org/raml-module-builder).


## Usage

To use this archetype, first build it and install it locally. 

```
mvn clean install
```

Once you receive a confirmation of the build success, go to the folder where you want to start the new project for your module.

```
mvn archetype:generate              	\
  -DarchetypeGroupId=org.folio        \
  -DarchetypeArtifactId=mod-folio     \
  -DarchetypeVersion=1.0-SNAPSHOT     \
  -DgroupId=org.folio                 \
  -DartifactId={module-name-here}
```

Verify the information in the prompts.

Once the new project folder is created, go into the new directory. You will need to place the directory under source control. Then, add the `raml-util` module. 

```
git init
git submodule add https://github.com/folio-org/raml ramls/raml-util
```

`raml-util` exposes traits shared by various RMB-based FOLIO modules.
