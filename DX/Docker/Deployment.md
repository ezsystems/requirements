# v2: Docker Deployment Requirements

## Objective

Deployment of Docker environments to multiple vendors. By its very nature,
Docker allows for this in a broad sense. It is in tooling such as Kubernetes,
Mesos, ECS, and Docker Swarm that we find some variance in vendor support, and
it is this variance which we seek to support with these requirements.

## Deployment Solution Requirements

### Firm
The feature MUST:
1. Be able to deploy to several container vendors

### Preferred
The feature SHOULD:
1. Use technology supported natively by the main vendors
  _(AWS, DigitalOcean, Google Cloud, Docker Cloud, Azure)_

### Bonus
The feature MAY:
1. Find ways to reuse parts of Docker configuration in a manner useful to those
  developers that are also working with Platform.sh configuration, and try to
  keep them somewhat in sync (even though Platform.sh does not support Docker at
  all, some parity between required versions, etc. may ease development with
  their service).
