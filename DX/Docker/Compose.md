# v2: Docker Compose Requirements

## Objective
To provide a default Docker Compose file or files, ready to use out-of-the-box.

https://docs.docker.com/compose/overview/

## Solution Requirements

### Firm
The feature MUST:
1. Provide best practice examples of environment configuration for use in new
  projects that gets you up and running quickly
1. Place environment in git for collaborative development and versioned with
  code
1. Allow new members to team to get started with environment with as few
  commands as possible

### Preferred
The feature SHOULD:
1. Be able to reconfigure eZ Platform via environment variables for all possible
  server configurations, such as:
  1. Single/cluster setup
  1. Cache using fs/memcached/redis
  1. Database using mysql/postgres
  1. Storage using fs/nfs/s3/..
  1. Search engine using db/solr/es
  1. Http cache using Symfony or Varnish
  1. Session stored on disk or in shared backend like memcached/redis/db
1. Be able to initiate with a database and binary dump

### Bonus
The feature MAY:
1. Be prepared for future supported technologies such as support for Fastly,
  mssql/oracle, etc.
