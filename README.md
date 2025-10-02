# Modular-Pendulum

Python script used to create n-body pendulum simulations in any media format supported by the Manim library (mp4, gif, etc).
The equations of motions are found using Kane's method via the Sympy library. The Integration is done using Scipy and the animation is done in ManimCE.

![Animate_ManimCE_v0 17 2](https://github.com/user-attachments/assets/18f9661a-5534-42b7-b3e3-8e05373b03f0)




## 🪄 Installation

### Prerequisites

- Python version > 3.0.0
- [conda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html) package manager

### 🐾 Step-by-Step Instructions

1. **Clone this repository to your local machine**

```
git clone https://github.com/djstillme/modular-pendulum.git
```

2. **Resolve dependencies by executing the following in the project directory**
   
```
conda env create -f environment.yml
```

> [!IMPORTANT]
> Ensure that you have the [conda-forge](https://conda-forge.org/) channel enabled, and `conda channel_priority` set to **flexible**
before trying to install the environment or it may not generate correctly — you may also need the [libmamba solver](https://conda.github.io/conda-libmamba-solver/user-guide/) enabled in your conda config.

## 📦 Usage

**Generate the animation using the following**

```
manim Animate.py Animate
```

After the animation has finished rendering, the output will be placed into the `media` folder in the projects root directory.

> [!IMPORTANT]
> Make sure you run this command in the `modp` conda environment, or whatever virtualenv you are using to manage the dependencies.

By default, manim generates an mp4 at 1080p at 60fps, if you want to change this — you can add parameters to the previous command, see the [ManimCE API](https://docs.manim.community/en/stable/guides/configuration.html) for more details. Keep in mind that whatever fps you set in `config.ini` should match what you execute the previous command with. For example if you want to render a 30 second animation at 144fps in 1440p you would need to edit **duration** and **fps** in `config.ini` to be 30/144 respectively and then execute the following command:

```
manim Animate.py Animate --fps 144 -r 2560,1440
```

> [!NOTE]
> The rendering time for the animation increases with the number of frames (`duration` × `fps`). Depending on these factors and your hardware’s performance, it may take anywhere from a few minutes to several hours to be fully completed.

### 🔧 Parameters

The customizable parameters are located in `config.ini`, and should be formatted as seen below in the **Example** column. A list of predefined colors can be found in the Manim documentation [here](https://docs.manim.community/en/stable/reference/manim.utils.color.manim_colors.html).

| Parameter         | Description                                 | Data Type     | Example                      |
|------------------|---------------------------------------------|---------------|------------------------------|
| n                | number of masses                            | int           | 4                            |
| b                | friction force                              | float         | 0.6                          |
| theta            | initial angle                               | list[float]   | 40 0 20 120                  |
| omega            | initial velocity                            | list[float]   | 4 2 1 0                      |
| gravity          | strength of gravitational force             | float         | 9.81                         |
| duration         | length of animation (in seconds)            | int           | 10                           |
| fps              | number of frames per second                 | int           | 144                          |
| lengths          | lengths of strings between masses           | list[float]   | 3 4 2 1                      |
| masses           | masses of each pendulum                     | list[float]   | 1 2 3 4                      |
| trails           | toggles trails behind masses                | bool          | true                         |
| strings          | toggles whether strings are visible         | bool          | false                        |
| ball_colors      | sets colors of masses                       | list[str]     | GREEN_E GOLD_B BLUE GREEN_E |
| string_colors    | sets colors of strings                      | list[str]     | WHITE                        |
| background_color | sets color of canvas                        | str           | BLACK                        |
| trail_length     | length of trail if trails are enabled       | int           | 100                          |




## 🎨 Gallery

![2](https://github.com/user-attachments/assets/9d2aa6a6-2337-4fc0-b2a4-e289a18a172a)

![3](https://github.com/user-attachments/assets/61d2abcc-06cc-45fb-bc39-570da067d8e6)

## References and Further Reading

[1] *T. Kane  and D.  Levinson. (1985). "Dynamics, theory  and applications."*

[2] *Hussain, Zakia & Azlan, Norsinnira. (2016). "KANE's method for dynamic modeling."*

[3] *Stoneking. Eric. (2013). "Implementation of Kane's Method for a spacecraft Composed of Multiple Rigid Bodies."*

[4] *Charles. S. (2019). "The Lagrangian Mechanics and Pseudo-Periodicity of The Many-Body Planar Pendulum System."*
