# Nexus Repository Manager Installation

## Overview
This project documents the installation and basic setup of Sonatype Nexus Repository Manager 3 on Ubuntu.
Nexus is used in CI/CD pipelines to store and manage build artifacts such as Maven packages, Docker images,
npm packages, and Helm charts.

## Use Case
- Central artifact storage
- Dependency caching
- Faster and reliable CI/CD builds
- Internal Docker and Maven registry

## Environment
- OS: Ubuntu 20.04 / 22.04
- Java: OpenJDK 11
- Tool: Nexus Repository Manager 3

## Installation
(Commands go here in table format)

## Access
- URL: `http://<server-ip>:8081`
- Default user: `admin`

## Notes
- Do not run Nexus as root
- Back up `/opt/nexusdata`

