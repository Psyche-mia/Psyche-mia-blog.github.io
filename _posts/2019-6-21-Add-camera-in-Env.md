---
layout: post
title: Add a camera in Open AI Gym customized Robotic Environment
---

- **Add a fixed camera in xml model**

Add camera element in ```<worldbody>```
```<camera name="top_camera" mode="fixed" pos="1.3 0.75 2" axisangle="0 1 0 0.1"/>```

- **Modify the camera_id in `robot_env.py`**

In the function `def render()` find ```self._get_viewer(mode).render(width, height, camera_id=0)```
Change the camera_id to select which camera to render the images

- **Get the images from the main**

```data = env.render(mode="rgb_array")```
data is the rgb images rendered from the selected camera.

*Call the env.render(mode="human") once before calling env.render(mode="rgb.array"). It's a bug in mujoco-py to be fixed*
