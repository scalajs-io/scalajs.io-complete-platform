ScalaJs.io Complete Platform Build
===================================

### Description

This project is used for locally building and publishing all components of the ScalaJs.io platform; including:

* [Core components](https://github.com/scalajs-io/scalajs.io) (Core, DOM/HTML, Node.js)
* All browser-based packages
* All npm packages

### Setup

The initial setup is simple. Just run the provided installer script - `install.py`. It will clone 
the ScalaJ.io repositories for the Core components, browser-based packages and npm packages.

**NOTE**: `install.py` has been provided to both clone the Scalajs.io repositories and keep them updated; 
meaning you'll want to periodically re-run the script to ensure you have the latest code.
However, in order to the script to operate properly, you must first install 
[GitPython](https://github.com/gitpython-developers/GitPython) Python plugin.

### Build Dependencies

* [SBT v0.13.13](http://www.scala-sbt.org/download.html)


### Build/publish the ScalaJs.io platform locally

```bash
 $ sbt clean publish-local
```

### Running the tests

Before running the tests the first time, you must ensure the npm packages are installed:

```bash
$ npm install
```

Then you can run the tests:

```bash
$ sbt test
```

### Artifacts and Resolvers

The following bundled artifacts are generated by this project: 

##### Complete platform bundle

```sbt
libraryDependencies += "io.scalajs" %%% "complete-platform" % "0.3.0.5"
```
##### MEAN Stack bundle (Node, MongoDB and Express.js)

```sbt
libraryDependencies += "io.scalajs.npm" %%% "mean-stack" % "0.3.0.5"
```

##### Angular.js bundle (including all associated components)

```sbt
libraryDependencies += "io.scalajs" %%% "angularjs-bundle" % "0.3.0.5"
```

Optionally, you may add the Sonatype Repository resolver:

```sbt   
resolvers += Resolver.sonatypeRepo("releases") 
```