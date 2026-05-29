# Core Namespace

## Overview

The `acs::core` namespace defines the base object model for ACS. It provides `i_object` for shared identity (a debug-facing tag/name) and `i_threaded_object` for managed periodic execution in derived objects.

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
