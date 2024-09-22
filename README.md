# Metarepo Template

This is a template repository for creating a metarepo for a set of services. It is intended to be used as a starting point for creating a new metarepo, and can be used as-is or as a reference for creating your own.

## Prerequisites

- Install [Tilt](https://tilt.dev/)

## Getting Started

`cp services.yaml.template services.yaml`, then configure the services as you see fit. To disable a service, simply comment it out. Any included services will be locally cloned. A local path override for each service can be specified using the `path` key. If no path is explicitly specified, the service will be cloned to `services/service-name` by default.

> 💡 _Note that if nested repos are cloned within this metarepo (such as with the default path of `services/service-name`) for a service and you open this metarepo in your IDE, the IDE may mark the directories as ignored due to the `.gitignore` patterns. To combat this, open the services you want to work on in their own directory (e.g. a separate unit in a VS Code workspace) rather than working with them from within this metarepo._

To get started after setting up the service configuration, run `tilt up`. The `Tiltfile` will automatically pull in resources from any nested `Tiltfile`s it discovers.
