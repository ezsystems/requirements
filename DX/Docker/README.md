# v2: Docker Requirements

## Objective

For new and existing Developers to get started with eZ Platform as quickly as
possible, with best-practice solutions for environments that can easily be used
for development, staging, and production.

## Motivation

"Docker" is an increasingly widening landscape of tools and techniques that all
centralize around a single theme: removing obstacles. In the past, Developers
had to do their best to get a localhost development environment installed and
configured to the best approximation of the environment(s) where their code
would eventually be deployed. Small variations between dependencies, versions,
and configurations could give a false positive during development: "it works on
my machine" was a common exclamation during those frustrating experiences where
ghost bugs would surface downstream.

With such a rich palette of tooling available in the world of Docker, it is
important that we not "do Docker for the sake of Docker". Rather, we seek to
achieve the same goals that the Docker suite of tools addresses: removing
obstacles.

To this end, it is important to keep the primary value of utilizing Docker in
clear focus: a Developer's computer should not consider any requirements, nor
should staging or production. Encapsulating functionality _within_ containers is
the key to achieving this goal.

Because containers may be built from images that are ready to run
out-of-the-box, composed as a pre-configured group of containers, or set up to
cluster and scale, there are numerous entry points into implementation of these
options. For eZ Platform, we will begin with a focus on the following:

1. Development / Staging / Production containers, composed by eZ and editable by
  developers to suite their needs.
1. Deployment, to address the Production element in greater detail
1. Migration, to facilitate common activities with database management
1. CLI Wrapping, to take the edge off of some of the more complex CLI commands

### General Use Cases
As a Developer, I want...
1. ...to get up and running quickly in development, without having to set up my
  environment manually.
1. ...to version environment configuration with my code so my whole team can
  reuse and co-maintain every aspect of our project, including use in a DevOps
  workflow for Continues Integration and Continuous Deployment
1. ...to version my database and binary content updates with my code for the
  same reasons.
1. ...to easily deploy to staging or production, reusing the same configuration
and data as is used locally; when data changes, to migrate existing data as I'm
rolling out updates.
1. ...to work on several projects at once with separated environments.
1. ...to work with standard industry tools for describing environments and
  deployment.

### Related Internal (eZ Systems Crew) Use Cases
1. As an eZ QA Engineer, I want to able to easily re-configure configurations
  for testing different supported environments.
1. As an eZ Support Engineer, I want to be able to re-configure configurations
  to replicate customer environments.
1. As an eZ PM, I want a demo image continuously built with the latest versions
  of the product under development using the same configurations with all
  features (e.g. Solr for Faceting).
1. As as eZ PS, I want to reuse same systems for training and demo use
  (Same needs as any Developer, to customize the content of the image easily).

#### Sub Goals
1. Some of the use cases above intentionally reflect aspects of
  [12factor](https://12factor.net/):
  1. Factor III: Server configuration is checked in with the code so it can be
    versioned.
  1. Factor X: Keeping development and production as similar as possible.
1. Lower the threshold for new developers to join an existing development
  project. (A big part of DX is reducing the barrier to entry!)
1. Minimize issues with missing dependencies/configuration during development.

## Docker and Docker-Compose Configuration Shared in eZ's GitHub Repository
See `Compose.md` in this directory.

## Deployments of Docker Environment to Multiple Vendors
See `Deployment.md` in this directory.

## Migration of Database and Binary Content for Deployments
See the file `Migration.md` in this directory.

## Wrapper Command for CLI
See the file `Wrapper.md` in this directory.
