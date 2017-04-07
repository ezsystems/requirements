# v2: Dockerized Migration Requirements
Migration for databases and binary content for deployment.

## Objective

For Developers to have a convenient solution for data migration, orchestrated in
Docker, allowing for zero-configuration actions, sharable with teams.

### Use Cases
As a Developer, I want...
1. ...to share database schema changes with my team
1. ...to migrate production from the old schema to the new one
1. ...to enjoy identical environments between developers, staging, and production
1. ...to optimize the size of my DB

## Migration Solution Requirements

### Firm
The feature MUST:
1. Provide means of dumping/updating my database and files to create a fully
  working environment.
1. Run within Docker containers

### Preferred
The feature SHOULD:
1. Be able to do this operation from dev to prod, and from prod back to dev
1. Be able to forward ENV variables to the desired app

### Bonus
The feature MAY:
1. Address migration from disparate databases, such as MySQL -> PostgreSQL
