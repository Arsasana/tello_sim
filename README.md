# tello_sim

**tello_sim** is a simple Python simulator (sim) that can be used by students to test their DJI tello flight plans before trying deploying them to a real drone. This supports the United States' Next Generation Science Standards for K12 related to [distinguishing between a model and the actual object, process, and/or events the model represents](https://ngss.nsta.org/Practices.aspx?id=2). It was inspired by the [easyTello](https://github.com/Virodroid/easyTello) library and uses it for the drone interface.

The sim outputs some basic plots which students can also use to see how actual flights compare to the simulated ones. The sim was developed for use in a Jupyter notebook or QT console so that the plots are displayed inline with the code print outputs. The sim currently supports a subset of the full DJI command set including: takeoff, land, forward, back, left, right, up, down, flip, cw, and ccw.

## Installation
<!-- To install the library, simply run:
```
pip install tello_sim
```
or to install from cloned source:
```
$ git clone https://github.com/Fireline-Science/tello_sim
$ cd tello_sim
$ pip install .
``` -->

**Note:** The sim requires pandas and is designed for use with Jupyter notebooks or QT consoles. Downloading and installing the [Anaconda distribution](https://www.anaconda.com/distribution/) of Python 3 is the recommended method for getting these data science packages.

## Sim Examples

The sim is built to run interactively in a Jupyter notebook or QT Console. The sim class outputs both text prompts and plots with each
simulated command.

Creating a simulated drone object in Python:
```python
from tello_sim import Simulator

my_drone = Simulator()
```
![](/images/ready.png)

```python
my_drone.takeoff()
```
![](/images/takeoff.png)

```python
my_drone.forward(40)
```
![](/images/forward.png)

```python
my_drone.cw(45)
```
![](/images/cw.png)

```python
my_drone.forward(50)
```
![](/images/forward_2.png)

```python
my_drone.land()
```
![](/images/land.png)

## Running Multiple Command Scripts in the Same Session
Note: if you are running multiple scripts to the drone, you may have to kill the process that binds the python process to the Tello port if you receive a `OSError: [Errno 48] Address already in use` error. You can search for and kill the process as follows in a linux-like console:

```
lsof -i:8889
kill XXXX
```
