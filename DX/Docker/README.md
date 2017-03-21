# v2: Docker and Deployment Requirements

## Objective

For new and existing eZ developers to get started as quickly as possible, with a best practice blueprint for
server environment that can easily be adapted to own needs.

### Use Cases
"As an eZ Developer, I want ":
- to get up and running quickly in development, without having to set up environment manually
- to version environment configuration with my code so whole team can reuse and co-maintain
  - and so environment configuration can be used in a devOps workflow for Continues Integration and Deployment
- to version database and binary content updates with my code for the same reasons.
- to easily be able to deploy to staging or production reusing same configuration and data as locally
  - on data changes migrate existing data when rolling out updates
- to work on several projects at once with separated environments
- to work with standard industry tools for describing environments and deployment

#### Sub goals
- Some of the use cases above reflects aspects of [12factor](https://12factor.net/):
  - Server configuration checked in with the code so it can be versioned
  - Keeping development and production as similar as possible
- Lower the threshold for new developers to join an existing development project
- Minimize issues with missing dependencies/configuration during development


#### Related internal use cases
- As an eZ Engineer, I want _(like eZ Developers)_ to get quickly up and running and share environment configuration with team
- As an eZ QA Engineer, I want to able to easily re-configure blueprint for testing different supported environments
- As an eZ Support Engineer, I want to be able to re-configure blueprint to replicate customer environments
- As an eZ PM, I want  a demo images continuously built with latest versions using same blue prints
  - Would need all features, so for instance Solr for Faceting
- As as eZ PS, I want to reuse same systems for training and demo use
  - Would need same needs as eZ Developer to customize the content of the image easily


## M1: Docker and Docker-compose configuration in Git

### Firm
The feature MUST:
- Provide best practice blueprint of environment for use in new projects that gets you up and running quickly
- Place environment in git for collaborative development and versioned with code
  - Implied: Allow new members to team to get started with environment with as few commands as possible

### Preferred
The feature SHOULD:
- Be able to reconfigure eZ Platform via environment variables for all possible server configurations
  - Single/cluster setup
  - Cache using fs/memcached/redis
  - Database using mysql/postgres
  - Storage using fs/nfs/s3/..
  - Search engine using db/solr/es
  - Http cache using Symfony or Varnish
  - Session stored on disk or in shared backend like memcached/redis/db
- Be able to initiate with a database and binary dump

### Bonus
The feature MAY:
- Be prepared for future supported technologies such as fastly, mssql/oracle, ..


## M2: Deployments of docker environment to multiple vendors

### Firm
The feature MUST:
- Be able to deploy to several container vendors


### Preferred
The feature SHOULD:
- Use technology supported natively by the main vendors _(AWS, Azure, Google Cloud, Docker Cloud, ..)_
  - Or at least some indications that it will be supported.

### Bonus
The feature MAY:
- Find ways to reuse parts of Docker configuration with Platform.sh configuration, and try to keep them somewhat in sync


## M3: Migration for database and binary content for Deployments

### Firm
The feature MUST:
- Provide means of dumping/updating my database and files to create a fully working environment

### Preferred
The feature SHOULD:
- Needs to be able to do this operation from dev to prod, and from prod back to dev


Todo:
- Consider splitting this up into 2-3 requirements to avodi milestone reference
