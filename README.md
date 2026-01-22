# 🗂️ Metarepo Template

This is a template repository for creating a metarepo that orchestrates multiple services for local development.

## Features

- 🚀 **Service Orchestration**: Unified local development across multiple repositories with [Tilt](https://tilt.dev)
- 🔗 **Flexible Configuration**: YAML-based service definitions with local path overrides
- 📦 **Auto-Discovery**: Automatically loads nested `Tiltfile`s from configured services
- 🛠️ **Developer Experience**:
  - Single command startup for entire stack
  - Hot reloading across all services
  - Service-level resource management
  - Easy spin up with [Tilt](https://tilt.dev)

## Prerequisites

- [Tilt](https://tilt.dev)

## Local Development

### Getting Started

1. Copy the template configuration:

```sh
cp services.yaml.template services.yaml
```

2. Configure the services as needed. To disable a service, comment it out. Any included services will be locally cloned.

3. Start the development environment:

```sh
tilt up
```

The `Tiltfile` will automatically pull in resources from any nested `Tiltfile`s it discovers.

### Configuration

Each service in `services.yaml` can specify:

| Key | Description |
|-----|-------------|
| `url` | Git repository URL for cloning |
| `path` | Local path override (defaults to `services/service-name`) |

> 💡 If nested repos are cloned within this metarepo and you open it in your IDE, directories may be marked as ignored due to `.gitignore` patterns. To work around this, open services in their own directory (e.g., a separate VS Code workspace unit).

> ⚠️ Services might have their own setup requirements, such as environment variable configuration. Consult each service's README to ensure all initial requirements are satisfied.

## License

The code in this repository is licensed under MIT, &copy; [Omni LLC](https://omni.dev). See [LICENSE.md](LICENSE.md) for more information.
