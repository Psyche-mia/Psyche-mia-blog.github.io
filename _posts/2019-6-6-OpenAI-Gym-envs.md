---
layout: post
title: OpenAI Gym Envs:Fetch
---

First we look at the structure of OpenAI Gym Envs code (shown below). [github code](https://github.com/openai/gym/blob/master/gym/envs/robotics/fetch_env.py)

![_config.yml]({{ site.baseurl }}/images/openaigym-envs.png)

The goal based environment is inherited from Env class.

**Goal based environment**

It functions just as any regular OpenAI Gym environment but it imposes a required structure on the observation_space. More concretely, the observation space is required to contain at least three elements, namely `observation`, `desired_goal`, and
`achieved_goal`. Here, `desired_goal` specifies the goal that the agent should attempt to achieve. `achieved_goal` is the goal that it currently achieved instead. `observation` contains the actual observations of the environment as per usual.

RobotEnv is inherited from Goal based environment.

**RobotEnv**

`Action space`: spaces.Box ranges in [-1, 1] with shape of `n_actions`

`Desired goal`: spaces.Box ranges in (-np.inf, np.inf) with shape of desired_goal ([[Error in source code?]](https://github.com/openai/gym/blob/master/gym/envs/robotics/robot_env.py))

`Achieved goal`: spaces.Box ranges in (-np.inf, np.inf) with shape of achieved_goal

`Observation`: spaces.Box ranges in (-np.inf, np.inf) with shape of observation
