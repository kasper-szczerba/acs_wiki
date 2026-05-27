# Core Namespace

## Overview

The `acs::core` namespace provides the foundational component system for the autonomous control system. It defines interfaces and base classes for managing component lifecycles, updates, and threaded execution.

## Namespace Contents

### Interfaces

- [i_object](interfaces/i_object.md)
- [i_threaded_object](interfaces/i_threaded_object.md)

### Implementations

- [object](implementations/object.md)
- [threaded_object](implementations/threaded_object.md)

## Inheritance Hierarchy

```mermaid
graph LR
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_implementations_object["object"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_implementations_threaded_object["threaded_object"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_interfaces_i_object["i_object"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_interfaces_i_threaded_object["i_threaded_object"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_implementations_object --> C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_implementations_threaded_object
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_interfaces_i_object --> C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_implementations_object
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_interfaces_i_object --> C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_interfaces_i_threaded_object
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_interfaces_i_threaded_object --> C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_implementations_threaded_object
```
