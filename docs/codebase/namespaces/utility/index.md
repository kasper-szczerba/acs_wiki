# Utility Namespace

## Overview

The `acs::utility` namespace contains helper components and interfaces for common functionality such as configuration file parsing and Zenoh communication.

## Namespace Contents

### Interfaces

- [i_toml_reader](interfaces/i_toml_reader.md)
- [i_zenoh_client](interfaces/i_zenoh_client.md)

### Implementations

- [toml_reader](implementations/toml_reader.md)
- [zenoh_client](implementations/zenoh_client.md)

## Inheritance Hierarchy

```mermaid
graph LR
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_implementations_object["object"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_interfaces_i_object["i_object"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_utility_implementations_toml_reader["toml_reader"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_utility_implementations_zenoh_client["zenoh_client"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_utility_interfaces_i_toml_reader["i_toml_reader"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_utility_interfaces_i_zenoh_client["i_zenoh_client"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_implementations_object --> C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_utility_implementations_toml_reader
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_implementations_object --> C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_utility_implementations_zenoh_client
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_interfaces_i_object --> C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_utility_interfaces_i_toml_reader
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_interfaces_i_object --> C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_utility_interfaces_i_zenoh_client
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_utility_interfaces_i_toml_reader --> C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_utility_implementations_toml_reader
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_utility_interfaces_i_zenoh_client --> C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_utility_implementations_zenoh_client
```
