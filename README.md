
# Tutorial: Building Tycho and bnd in One Gradle Project

## Goals

* Drive both a Tycho build and a bnd build with a parent / root gradle project
* Generate an OSGi R5 repository index for a p2 update site
* Use this index as a repository source in bndtools 

## Requirements

* bndtools 4.0


## Details

Refer to the following:

* Root project [settings.gradle](settings.gradle) showing how to include bnd projects
* Root project [build.gradle](build.gradle) for the PDE task
* bnd's [build.gradle](bnd/build.gradle) to show how to refresh the repo and use it in a previously configured bnd project
* [build.gradle](pde/build.gradle) used to run Tycho
* The `-plugin.5.Pde` repository [configuration](bnd/cnf/build.bnd)

## Bugs / Issues / Todos

* Only re-build the Tycho project when needed not each time, and only once even if `assemble` and `check` are called separately. 
* The bnd repository configuration contains cross-project references to the index file in PDE land.
