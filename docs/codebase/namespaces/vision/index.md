# Vision Namespace

## Overview

The `acs::vision` namespace contains components for camera access, scene understanding, and visualization. It implements the detection pipeline for obstacles using ZED stereo camera hardware.

## Namespace Contents

### Interfaces

- [i_camera](interfaces/i_camera.md)

### Implementations

- [camera](implementations/camera.md)
- [matrix_converter](utility/matrix_converter.md)

## Inheritance Hierarchy

```mermaid
graph LR
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_implementations_threaded_object["threaded_object"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_interfaces_i_threaded_object["i_threaded_object"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_vision_implementations_camera["camera"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_vision_interfaces_i_camera["i_camera"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_vision_utility_matrix_converter["matrix_converter"]
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_implementations_threaded_object --> C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_vision_implementations_camera
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_core_interfaces_i_threaded_object --> C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_vision_interfaces_i_camera
    C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_vision_interfaces_i_camera --> C__DEV_vs_projects_acs_wiki_docs_codebase_namespaces_vision_implementations_camera
```
