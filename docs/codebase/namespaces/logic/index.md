# Logic Namespace

## Overview

The `acs::logic` namespace contains navigation and behavior coordination components that consume perception and GPS inputs to produce steering and runtime state decisions.

## Namespace Contents

### Implementations

- [navigation_manager](navigation_manager.md)
- [state_machine](state_machine.md)
- [steering_handler](steering_handler.md)

## Inheritance Hierarchy

```mermaid
graph LR
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_implementations_object["object"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_logic_navigation_manager["navigation_manager"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_logic_state_machine["state_machine"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_logic_steering_handler["steering_handler"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_implementations_object --> C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_logic_navigation_manager
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_implementations_object --> C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_logic_state_machine
```
