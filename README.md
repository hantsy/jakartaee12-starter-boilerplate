# Jakarta EE 12 Starter Boilerplate

[![build](https://github.com/hantsy/jakartaee12-starter-boilerplate/actions/workflows/build.yml/badge.svg)](https://github.com/hantsy/jakartaee12-starter-boilerplate/actions/workflows/build.yml)
[![arq-glassfish-managed](https://github.com/hantsy/jakartaee12-starter-boilerplate/actions/workflows/arq-glassfish-managed.yml/badge.svg)](https://github.com/hantsy/jakartaee12-starter-boilerplate/actions/workflows/arq-glassfish-managed.yml)
[![arq-glassfish-remote](https://github.com/hantsy/jakartaee12-starter-boilerplate/actions/workflows/arq-glassfish-remote.yml/badge.svg)](https://github.com/hantsy/jakartaee12-starter-boilerplate/actions/workflows/arq-glassfish-remote.yml)

A clean starter template for Jakarta EE 12 applications, targeting GlassFish 9 (Jakarta EE 12 milestones). It demonstrates modern Jakarta EE development — CDI + JPA data access, JAX-RS REST services, a Jakarta Faces web UI, and JMS — together with [Arquillian](https://arquillian.org) integration tests.

## Prerequisites

* **Java 25**
* **Maven 3.9+** (Maven 4 is recommended)

## Build and Run

* **GlassFish** via [Cargo Maven Plugin](https://codehaus-cargo.github.io/cargo/GlassFish+9.x.html):

  ```bash
  mvn clean package cargo:run -Pglassfish
  ```

* **Embedded GlassFish** via [Embedded GlassFish Maven Plugin](https://github.com/eclipse-ee4j/glassfish-maven-embedded-plugin):

  ```bash
  mvn clean package embedded-glassfish:run -Pglassfish-embedded
  ```

## Running Arquillian Tests

* **GlassFish Managed**:

  ```bash
  mvn clean verify -Parq-glassfish-managed
  ```

* **GlassFish Remote** (requires an already-running GlassFish instance, local or Docker):

  ```bash
  mvn clean verify -Parq-glassfish-remote
  ```

The GitHub Actions workflows use Docker service containers to run the server automatically. See the [workflow files](.github/workflows/) for the Docker configuration.
