# Lumen

## Project Description
Lumen is an project that will load obj and gltf scenes into a scenehiearchy and enable the user to view the geometry and materials within an interactive window.  The user will be able to manipulate the camera as well as the lights in the scene.

## Project dependencies

Lumen depends on the following libraries:

* imgui
* Vulkan
* gltf
* Cmake

## Target platforms

Lumen will support Android and Windows

## Software architecture

Lumen will have the following software components:

### LumenModel

LumenModel shall be responsible for maintaining the data for the application.  Namely:

* the scene description, the object geometry, and materials
* camera that represents the user viewpoint and parameters associated with the camera
* any lights defined by the user and associated parameters

### LumenView

LumenView shall be responsible for all of the setup to create the GUI and orchestrating the calls to Vulkan to process the geometry for shading and display

### LumenController

LumenController shall be responsible for the application logic, the reading of launch options, and managing the interface between the model and the view

## Requirements

### LumenModel

LumenModel shall offer the following capabilities:

SceneModel
CameraModel
LightModel

### LumenView

imguiView
Vulkan routines to setup, refresh, and teardown the interface to Vulkan

### LumenController

* application startup settings
* creation of LumenModel and LumenViewer
* setting up initial parameters to lumen model and lumen viewer
* control logic to interface to LumenView and receive user input and respond by providing data from LumenModel
* starting the application event processing loop
* teardown and destruction of LumenModel and LumenViewer upon exit

