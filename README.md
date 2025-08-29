# World Model

 Curated list of papers, resources for AI World Models. World models aim to learn the dynamics of our world, allowing an AI to simulate or "dream"
 about the future internally.

## Table of Contents
- [Core Technical Challenges & Insights](#core-technical-challenges--insights)
- [Foundational Papers 📜](#foundational-papers-)
- [Key Architectures & Evolution 🚀](#key-architectures--evolution-)
- [Large-Scale Generative World Models ✨](#large-scale-generative-world-models-)
- [Open Source Implementations 💻](#open-source-implementations-)
- [Key Application Areas 🎯](#key-application-areas-)
- [Useful Resources](#useful-resources-)

## Core Technical Challenges & Insights
- **High-Dimensional Perception:** How to compress complex visual inputs (like video) into a meaningful, low-dimensional representation.
  - **Solutions:** Variational Autoencoders (VAEs), Transformer-based Encoders.
- **Long-Term Temporal Dependencies:** How to enable the model to remember events that happened long ago but are critical for the future.
  - **Solutions:** Recurrent Neural Networks (RNNs/LSTMs), **Transformers** (superior).
- **Computational Complexity:** Simulating in pixel space is extremely expensive.
  - **Solution:** Perform simulation and prediction in a compact **Latent Space**.
- **Sample Efficiency:** How to learn a model with as little real-world interaction as possible.
  - **Solution:** Conduct extensive training within a fast, internal "dream."
## Foundational Papers 📜
- **[World Models](https://arxiv.org/abs/1803.10122)** (Ha & Schmidhuber, 2018)
   - **Contribution:** First to clearly propose the V-M-C (Vision-Memory-Controller) architecture and demonstrate the feasibility of training an agent entirely within its
      own generated "dream." This is the intellectual starting point for all modern world models.
- **The Dreamer Series** (Danijar Hafner et al., 2019-2023)
   - **[Dream to Control: Learning Behaviors by Latent Imagination](https://arxiv.org/abs/1912.01603)** (Dreamer)
   - **[Mastering Atari with Discrete World Models](https://arxiv.org/abs/2010.02193)** (DreamerV2)
   - **[Mastering Diverse Domains through World Models](https://arxiv.org/abs/2301.04104)** (DreamerV3)
   - **Contribution:** As the most direct successor to the "World Models" paper, this series combines latent space learning with gradient-based optimization. It has achieved
      state-of-the-art results on many reinforcement learning benchmarks and is one of the most widely used models in both industry and academia.
- **[Learning Latent Dynamics for Planning from Pixels (PlaNet)](https://arxiv.org/abs/1811.04551)** (Hafner et al., 2019)
   - **Contribution:** The direct precursor to the Dreamer series. This paper introduced a model that learns a world model purely from images and then efficiently plans
     future actions by "shooting" thousands of potential trajectories in the compact latent space. It established the effectiveness of latent-space planning.
For Robotics:
- **[Deep Visual Foresight for Planning Robot Motion](https://arxiv.org/abs/1812.00568)** (Finn et al., 2019)
  - **Contribution:** A landmark paper in robotics that demonstrates how a robot can use a video-prediction model (a form of world model) to "foresee" the outcome of its
     potential actions. The robot could then choose the action sequence that led to the desired outcome, enabling it to perform complex manipulation tasks like pushing objects
     around.
For Autonomous Driving:
- **[GAIA-1: A Generative World Model for Autonomous Driving](https://arxiv.org/abs/2309.17080)** (Wayve, 2023)
  - **Contribution:** A prime example of a large-scale world model built specifically for autonomous driving. GAIA-1 can generate realistic and controllable driving
     scenarios, which can be used to train and test self-driving systems in a closed loop, significantly accelerating development.


## Key Architectures & Evolution 🚀
Architectural innovations that pushed the boundaries of what world models can do.
- **[Transformers are Sample-Efficient World Models (IRIS)](https://arxiv.org/abs/2209.00588)** (Micheli et al., 2023)
   - **Contribution:** Proved that using a Transformer as the core dynamics model can dramatically improve sample efficiency. This marked a paradigm shift in world model
      architecture from RNNs to the more powerful Transformer.
## Large-Scale Generative World Models ✨
   Models that apply the world model concept to massive datasets, resulting in astonishing generative capabilities.
   - **[Genie: Generative Interactive Environments](https://sites.google.com/view/genie-2024)** (Google DeepMind, 2024)
     - **Contribution:** An 11-billion parameter foundation world model that can generate interactive, playable 2D platformer worlds from a single image. It demonstrates the
      immense potential of learning world rules and interactivity from massive, unlabeled video datasets.
   - **[Sora: Video generation models as world simulators](https://openai.com/research/video-generation-models-as-world-simulators)** (OpenAI, 2024)
      - **Contribution:** While OpenAI calls it a video generation model, their technical report explicitly states that Sora is trained as a "world simulator." Its ability to
      generate videos with a high degree of physical realism, long-term coherence, and object permanence indicates the existence of an extremely powerful and complex internal
      world model.
## Open Source Implementations 💻
   - **DreamerV3 (Official):** [https://github.com/danijar/dreamerv3](https://github.com/danijar/dreamerv3)
      - The official implementation of DreamerV3 by Danijar Hafner. This is the most recommended codebase for studying and researching world models.
   - **World Models (Original):** [https://github.com/worldmodels/worldmodels.github.io](https://github.com/worldmodels/worldmodels.github.io)
      - The official website and related code for the original 2018 paper.
## Key Application Areas 🎯
   - **🤖 Robotics**
      - Learning complex grasping and manipulation tasks in "imagination" before transferring the learned policy to a real-world robot, which is both safer and more efficient.
   - **🚗 Autonomous Driving**
      - Generating vast numbers of rare and dangerous driving scenarios ("long-tail scenarios") for training and testing autonomous systems.
      -  - Predicting the behavior of other vehicles and pedestrians on the road to make safer plans.
   - **🎮 Gaming & Interactive Media**
      - Automatically generating endless, novel game levels and virtual worlds.
      - Training smarter NPCs that can anticipate player actions and react intelligently.
## Useful Resources
A collection of blog posts and videos that explain the core concepts of world models in an intuitive way.
- [From Video Generation to World Model](https://world-model-tutorial.github.io)
- [Can agents learn inside of their own dreams?](https://worldmodels.github.io)
- [World Models](https://rohitbandaru.github.io/blog/World-Models/)
- [World models — a reinforcement learning story](https://smartlabai.medium.com/world-models-a-reinforcement-learning-story-cdcc86093c5)
- [1X World Model](https://www.1x.tech/discover/redwood-ai-world-model)
