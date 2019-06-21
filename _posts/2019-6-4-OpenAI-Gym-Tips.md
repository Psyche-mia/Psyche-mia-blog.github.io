---
layout: post
title: OpenAI Gym Tips
---

## Functions
- **FlattenDictWrappe()**
Flattens selected keys of a Dict observation space into an array.

## Envs
- **Get spaces from Dict**

Example: In Fetch environment to get observation space from ```Dict(achieved_goal:Box(3,), desired_goal:Box(3,), observation:Box(10,))```

```env.observation_space.spaces["observation"]```

- **Mujoco Env**

Call ```env.render(mode="human")``` once before calling ```env.render(mode="rgb_array")```
This may be a bug in mujoco-py to be fixed
