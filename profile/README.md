# OpenVCS

OpenVCS is an experimental, extensible version control system client built with Rust, Tauri, and TypeScript.

The project explores how a modern VCS client can be designed when performance, extensibility, and explicit architecture boundaries are treated as first class concerns.

Status: Experimental  
Nothing in OpenVCS is currently considered stable.  
APIs, plugin protocols, file formats, and internal architecture may change without notice.

---

## Platform Support

OpenVCS is developed with a Linux first focus.

Linux is the primary development platform and the main priority.

Windows is supported but is not the primary target platform.

macOS is not currently supported. Support may be considered in the future if there is sufficient community interest and contribution.

---

## What OpenVCS Is

OpenVCS is built around a plugin based architecture.

Core functionality is kept intentionally small. Version control backends, integrations, extended behaviour, and theming are expected to live in plugins rather than in the application itself.

Git is supported first. It is not assumed to be the only backend long term.

The project prioritises:

- Clear separation between the application, core contracts, and plugins
- External plugin execution with explicit boundaries
- A distribution format for plugins rather than source based loading
- Plugin based theming rather than hard coded UI styling
- Linux desktop workflows

---

## Repositories

This organisation is split into multiple repositories with distinct responsibilities.

### OpenVCS

The main desktop application.

This repository contains the UI, application state, the plugin host runtime, and theme loading logic.

### OpenVCS Core

Shared core types and contracts.

This includes protocol definitions, backend interfaces, and shared runtime abstractions used by the application and plugins.

### OpenVCS SDK

Tooling intended for plugin authors.

This repository provides utilities for building, validating, and packaging plugins into `.ovcsp` bundles. This includes support for both functional plugins and theme plugins.

### OpenVCS Plugin Git

The reference Git plugin.

This repository implements Git support using the OpenVCS plugin protocol and serves as a practical example of a functional plugin.

---

## Plugin System

The OpenVCS plugin system is experimental.

Plugins are distributed as `.ovcsp` bundles and executed as isolated external processes. Communication with the host is performed over a defined protocol.

Plugins may provide functionality, integrations, or UI themes.

There is no stable plugin API. Breaking changes are expected.

---

## Contributing

Contributions are welcome with the understanding that the project is still evolving.

Design changes, refactors, and breaking changes are intentional at this stage.

Linux focused contributions are especially useful.

---

## License

OpenVCS is licensed under GPL 3.0 unless stated otherwise.

---

## Philosophy

OpenVCS is not intended to replicate existing tools.

The project exists to explore how a Linux first, extensible VCS client can be built with modern systems tooling and explicit architectural boundaries.

Stability will come later. Architecture comes first.
