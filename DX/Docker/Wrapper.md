# v2: Dockerized Deployment Wrapper

## Objective

To facilitate common tasks performed with eZ Platform and its entourage of
technologies, a command-line wrapper for frequently performed activities is
desirable. Given that Docker unifies Development, Staging, and Production
environments, such tooling will be used to unify development environments as
well using Docker. The solution will be "aware" of the difference between
running on a clustered configuration, and provide assistance to the developer in
issuing relevant commands to manage common tasks in this arena.

Deliverable: The solution shall be one _command_, with options, documented with
instructions, runnable on Unix, Linux, Mac, and Windows development, staging,
and production machines, enabling a single approach to common tasks regardless
of environment.

## Wrapper Solution Requirements

### Firm
The solution MUST:
1. Run _inside_ of a Docker container, to unify environments across all systems,
  and thus equally usable on Unix, Linux, Windows, and macOS machines.
1. Run _only_ when non-destructive tasks are verified by safety checks in the
  code, or destructive tasks are confirmed by the user on the CLI with a YES/no
1. Implement _best practices_ as generally accepted and recommended by the
  leaders in the Docker community and prevailing usage patterns in the industry
1. Respect the other requirements set forth in this section (e.g. requirements
  given in Compose.md, Deployment.md, Migration.md, and the Use Cases in
  README.md).
1. Be modular, following the UNIX approach to piping collections of commands, in
  which each command _does one thing_.
1. Keep and expose logs to the developer

### Preferred
The solution SHOULD:
1. Be _fast_
1. Utilize a numbered menu of common activities for guided selection
1. Be capable of reporting errors back to eZ when they occur
1. Be self-documenting
1. Allow for custom configuration of the tool itself, and sharing of that config

### Bonus
The solution MAY:
1. Achieve universal compatibility using helpers (additional requirements on top
  of Docker), so long as the primary requirement is only to have a working
  Docker install on a given machine (e.g., a Docker container may run code
  inside the container that modifies the host with confirmation by the user).
1. Be runnable outside of a Docker environment, but only by the user's choice
1. Implement ASCII art
