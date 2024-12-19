# Dockerfile Bug: Inconsistent Builds Due to `latest` Tag

This repository demonstrates a common error in Dockerfiles: using the `latest` tag for the base image.  Using `latest` can lead to unexpected behavior and broken builds because the image content may change without notice.  This is especially problematic in production environments.

## Bug

The provided `Dockerfile` uses `ubuntu:latest` as the base image.  This is bad practice since `latest` is not a fixed, immutable version.  Subsequent builds might run on different base image versions leading to inconsistencies.

## Solution

The `Dockerfile_solution` demonstrates the correct approach. It uses a specific version tag (e.g., `ubuntu:22.04`) instead of `latest`. This guarantees consistent build environments across different times and contexts.