---
layout: post
title: Register a customized Robotic Environment in Open AI Gym
---

- **Locate Gym package path**

```>>> import gym```

```>>> print (gym.__file__)```

The path is like ```/home/user/.local/lib/python3.6/site-packages/gym/__init__.py```

- **Add `my_env.py`**

`my_env.py` contains `My_Env` which is the environment name
Add `my_env.py` to ```/gym/gym/envs/robotics/fetch```

- **Register the environment**

In ```/gym/gym/envs/robotics/__init__.py```

Add ```from gym.envs.robotics.fetch.my_env import My_Env```

In ```/gym/gym/envs/__init__.py```

Add ``` register(
          id='MyEnv{}-v1'.format(suffix),
          entry_point='gym.envs.robotics:My_Env'
          )
    ```
