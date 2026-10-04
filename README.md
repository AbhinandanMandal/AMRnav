# Autonomous Mobile Robot Navigation
This is the implementation of autonomous mobile robot navigation using deep reinforcement learning framework in 2D grid with expert warm start path planning algorithm in GNSS denied environment.
The initial idea was taken from,
1. [Path Planning of Autonomous Mobile Robot in Comprehensive Unknown Environment Using Deep Reinforcement Learning](https://ieeexplore.ieee.org/document/10475692/).
2. [AutoNavRL](https://github.com/AbhinandanMandal/AutoNavRL)

<img width="420" height="236" alt="multi_obs_compressed" src="https://github.com/user-attachments/assets/59a04c3a-ca3f-47c3-84f8-0ee538c9eba2" />
<img width="934" height="758" alt="Screenshot 2026-10-05 005141" src="https://github.com/user-attachments/assets/3a5dfa5d-de3d-4e92-a4e6-cb682cbeb8df" />



## Sensors & Algorithm
For this project, three fundamental sensors `LiDAR`, `Camera` and `IMU`have been taken into consideration,   
Using the above three sensors, the following analysis has been done extensively on multiple scenarios and conditions. 

Following testcases were running using four algorithm,
1. [DQN](https://medium.com/@qempsil0914/deep-q-learning-part2-double-deep-q-network-double-dqn-b8fc9212bbb2)
2. [Double DQN](https://medium.com/@qempsil0914/deep-q-learning-part2-double-deep-q-network-double-dqn-b8fc9212bbb2)
3. [Dueling DQN](https://medium.com/@sainijagjit/understanding-dueling-dqn-a-deep-dive-into-reinforcement-learning-575f6fe4328c)
4. IDDQN (propsoed in the following research paper)

   
## Project Structure
```text
AutoUAVNav/
│
├── PlotFunction/
│   ├── PlotDualSensorFusion.py
│   └── PlotIndividualSensorFusion.py
│
├── QNetwork/
│   ├── DeepQNetwork.py
│   └── DuelingQNetwork.py
│
├── TrainAgent/
│   ├── TrainAgentDualSensorFusion.py
│   └── TrainAgentIndividualSensorFusion.py
│
├── Utils/
│   ├── ExpertWarmStart.py
│   ├── HyperparametersConfig.py
│   ├── ObstacleGrid2D.py
│   ├── ReplayBuffer.py
│   ├── RLAgent.py
│   └── SensorFusionEnv.py
│
├── DualSensorComparisonDQN.py
├── DualSensorComparisonDuelDQN.py
├── DualSensorComparisonDDQN.py
├── DualSensorComparisonIDDQN.py
│
├── IndividualSensorComparisonDQN.py
├── IndividualSensorComparisonDuelDQN.py
├── IndividualSensorComparisonDDQN.py
└── IndividualSensorComparisonIDDQN.py
```


In the following `individual` sensor represents only `LiDAR`, `Camera`, `IMU`. And `dual` sensors represents `LiDAR + IMU`, `Camera + IMU`, `LiDAR + Camera`, `LiDAR + Camera + IMU`.

## Analytical Results
Episodic result of `LiDAR + Camera + IMU` with varying reinforcement learning algorithm.
<img width="1800" height="900" alt="sensorfusion_rl_episode_reward_moving_average" src="https://github.com/user-attachments/assets/e14a98a5-807c-46ec-9ea5-3baf2101f2dc" />

### Individual Sensor's
Episodic result of individual sensors with `DQN` algorithm
<img width="1800" height="900" alt="individual_sensor_reward_curves_DQN" src="https://github.com/user-attachments/assets/b5eb13a0-e06e-4c2c-99ba-b9874970fb47" />

Episodic result of individual sensors with `DDQN` algorithm
<img width="1800" height="900" alt="individual_sensor_reward_curves_DDQN" src="https://github.com/user-attachments/assets/9cefa195-59e4-44e2-98fb-9434cc9e17f9" />

Episodic result of individual sensors with `DuelDQN` algorithm
<img width="1800" height="900" alt="individual_sensor_reward_curves_DuelDQN" src="https://github.com/user-attachments/assets/439f70f5-39f7-47a5-bdbf-04f1992f9491" />

Episodic result of individual sensors with `IDDQN` algorithm
<img width="1800" height="900" alt="individual_sensor_reward_curves" src="https://github.com/user-attachments/assets/c5ca25ac-f198-4058-b6ae-e5c71a31d6d4" />


### Dual Sensor's
Episodic result of dual sensors with `DQN` algorithm
<img width="1800" height="900" alt="dual_sensor_reward_curves_DQN" src="https://github.com/user-attachments/assets/8f449115-645e-4c9b-86c9-bc2c3b3c1112" />

Episodic result of dual sensors with `DDQN` algorithm
<img width="1800" height="900" alt="dual_sensor_reward_curves_DDQN" src="https://github.com/user-attachments/assets/18a96fda-5167-4b8d-87dd-15314b7cc10b" />

Episodic result of dual sensors with `DuelDQN` algorithm
<img width="1800" height="900" alt="dual_sensor_reward_curves_DuelDQN" src="https://github.com/user-attachments/assets/c17a3a90-755d-437f-be16-12e366e094de" />

Episodic result of dual sensors with `IDDQN` algorithm
<img width="1800" height="900" alt="dual_sensor_reward_curves_IDDQN" src="https://github.com/user-attachments/assets/b0afff54-1a01-430f-ad59-5b979b3992fe" />

**Made with ☕️ by Abhinandan**

