# Namespaces

This page indexes the namespace documentation and the project-wide inheritance graph.

## Namespace Pages

- [Core](core/index.md)
- [Gui](gui/index.md)
- [Opengl](opengl/index.md)
- [Utility](utility/index.md)
- [Vision](vision/index.md)

## Inheritance Graph

```mermaid
graph LR
    i_camera["i_camera"] --> camera["camera"]
    i_floor_detector["i_floor_detector"] --> floor_detector["floor_detector"]
    i_glfw_window["i_glfw_window"] --> glfw_window["glfw_window"]
    i_object["i_object"] --> i_glfw_window["i_glfw_window"]
    i_object["i_object"] --> i_threaded_object["i_threaded_object"]
    i_object["i_object"] --> i_toml_reader["i_toml_reader"]
    i_object["i_object"] --> i_widget["i_widget"]
    i_object["i_object"] --> i_widget_controller["i_widget_controller"]
    i_object["i_object"] --> i_zenoh_client["i_zenoh_client"]
    i_object["i_object"] --> object["object"]
    i_obstacle_detector["i_obstacle_detector"] --> obstacle_detector["obstacle_detector"]
    i_threaded_object["i_threaded_object"] --> i_camera["i_camera"]
    i_threaded_object["i_threaded_object"] --> i_floor_detector["i_floor_detector"]
    i_threaded_object["i_threaded_object"] --> i_obstacle_detector["i_obstacle_detector"]
    i_threaded_object["i_threaded_object"] --> i_threaded_widget["i_threaded_widget"]
    i_threaded_object["i_threaded_object"] --> threaded_object["threaded_object"]
    i_threaded_widget["i_threaded_widget"] --> threaded_widget_host["threaded_widget_host"]
    i_toml_reader["i_toml_reader"] --> toml_reader["toml_reader"]
    i_widget["i_widget"] --> widget_host["widget_host"]
    i_widget_controller["i_widget_controller"] --> widget_controller["widget_controller"]
    i_zenoh_client["i_zenoh_client"] --> zenoh_client["zenoh_client"]
    object["object"] --> glfw_window["glfw_window"]
    object["object"] --> threaded_object["threaded_object"]
    object["object"] --> toml_reader["toml_reader"]
    object["object"] --> widget_controller["widget_controller"]
    object["object"] --> widget_host["widget_host"]
    object["object"] --> zenoh_client["zenoh_client"]
    threaded_object["threaded_object"] --> camera["camera"]
    threaded_object["threaded_object"] --> floor_detector["floor_detector"]
    threaded_object["threaded_object"] --> obstacle_detector["obstacle_detector"]
    threaded_object["threaded_object"] --> threaded_widget_host["threaded_widget_host"]
    threaded_widget_host["threaded_widget_host"] --> camera_widget["camera_widget"]
    widget_host["widget_host"] --> about_widget["about_widget"]
```
