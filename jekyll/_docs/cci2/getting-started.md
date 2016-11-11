---
layout: classic-docs
title: "CircleCI 2.0: An Introduction"
category: [getting-started]
order: 1
description: "Getting Started with CircleCI 2.0"
---

CircleCI 2.0 is a replacement container infrastructure for running builds on CircleCI. It takes advantage of some recent technology to provide more flexibility in how build environments are created and managed.

## Build Execution Environment and Docker

CircleCI 2.0 offers tighter integration with Docker, which enables:

* Custom build images: Use any public image on Docker Hub.

* Container composition: Construct a build environment with multiple composed containers.

This flexibility allows you to reduce build preparation time before tests.  Also, directly managing the base image enables consistent and predictable builds.

## Performance

CircleCI 2.0 introduces many changes that are aimed to improve build times:

* Independent tasks within parallel builds: In the current CircleCI build environment, a step in a parallel build will only run if the previous step finished executing on all build containers. In CircleCI 2.0, each container executes independently, breaking the lockstep process in the existing build environment.

* Configurable CPU/RAM resources: Projects that are compile-heavy and require lots of memory would benefit from having beefier containers rather than multiple containers. CircleCI 2.0 allows configuration of CPU/RAM on a per-build basis.

## Local build environment

CircleCI 2.0 offers a build agent binary for running builds locally. This speeds up iteration of configuration work and debugging problems that appear within builds.

## Flexible Customizations

Steps like caching and artifacts management are no longer hard-coded "special" steps. Instead, they are fully configurable and user-managed.

CircleCI 2.0 also aims to support third party extensions/plugins for special commands and common build patterns.

# Installation

CircleCI 2.0 is currently in a private opt-in program.  Please contact your customer success manger or email [beta@circleci.com](mailto:beta@circleci.com) to whitelist your project for CircleCI 2.0.

Once whitelisted, you can configure `circle.yml` for CircleCI 2.0.  This lets you test builds on CircleCI 2.0 on a separate branch, leaving your other builds running on the existing CircleCI infrastructure.