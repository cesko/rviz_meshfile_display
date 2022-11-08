# Rviz Meshfile Display

**author:** Christian Koch <christian.koch@dfki.de> 

**maintainer:** Christian Koch <christian.koch@dfki.de> 


Publish a meshfile to display in rviz

## Usage

'''
roslaunch rviz_meshfile_display rviz_meshfile_display meshfile:='package://path/to/meshfile.stl'
'''

All the parameter listed below can be used as launch-arguments.

## Node: Rviz Meshfile Display

Publish a meshfile to display in rviz

This node provides periodically triggered update loops:
 - **main** (1 Hz) 

### Interface

#### Static Parameters

| Parameter      | Type   | Default    | Description           |
| -------------- | ------ | ---------- | --------------------- |
| `meshfile` | string |  | location of meshfile |
| `frame_id` | string | world | Parent frame |
| `maker_ns` | string |  | Marker namespace |
| `x` | double | 0.0 | Positon X |
| `y` | double | 0.0 | Positon Y |
| `z` | double | 0.0 | Positon Z |
| `R` | double | 0.0 | Rotation around X (Roll) |
| `P` | double | 0.0 | Rotation around Y (Pitch) |
| `Y` | double | 0.0 | Rotation around Z (Yaw) |
| `angle_in_degree` | bool | false | When true, angles (RPY) are interpreted as degrees |


#### Dynamic Parameters

| Parameter | Type | Default | Description |
| --------- | ---- | ------- | ----------- |
| `color_red` | double | 0.5 | red-value |
| `color_green` | double | 0.5 | green-value |
| `color_blue` | double | 0.5 | blue-value |
| `color_alpha` | double | 0.5 | alpha-value |
| `scale_x` | double | 1.0 |  |
| `scale_y` | double | 1.0 |  |
| `scale_z` | double | 1.0 |  |
| `use_embedded_materials` | bool | false | use embedded materials of meshfile |


#### Published Topics

| Publisher | Type | Description |
| --------- | ---- | ----------- |
| `visualization_marker`  | visualization_msgs/Marker | Rviz marker topic |




 