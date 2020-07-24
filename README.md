# Tanzu Build Service

This repository will outline the instructions for setting up Tanzu Build Service for building container images for an ASP.NET Core MVC Web application.

## Full Documentation

The official documentation for Tanzu Build Service can be found at the following link. Be sure to select the appropriate version from the dropdown at the top of the page.

		https://docs.pivotal.io/build-service/0-2-0/index.html

The instructions in this repository are based on version 0.2.0.

## Introduction

This tutorial will be using the following resources.

* GitHub, source code repository for an ASP.NET Core 3.1 MVC Web application.
* DockerHub, container registry for the images built.
* Azure Kubernetes Service, the cluster environment in which Tanzu Build Service will run.

### Installation

* docker login IMAGE-REGISTRY
* duffle relocate -f build-service-${version}.tgz -m relocated.json -p IMAGE-REGISTRY
* duffle install BUILD-SERVICE-INSTALLATION-NAME -c credentials.yml --set kubernetes_env=CLUSTER-NAME --set docker_registry=DOCKER-REGISTRY --set docker_repository=DOCKER-REPOSITORY --set registry_username="REGISTRY-USERNAME" --set registry_password="REGISTRY-PASSWORD" --set custom_builder_image="BUILDER-IMAGE-TAG" -f build-service-${version}.tgz -m relocated.json
* kp custom-cluster-builder list