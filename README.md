# WindFarmOptimization
## Using Particle Swarm Optimization and Circle Packing
### Approach 1:
### Wind Farm Optimization Using MINIMIZATION TECHNIQUES.
#### Problem-
To optimize placement of Windmills in a Wind Farm constrained by perimeter, distance and subject to Wake Effect.

#### Solution-
To solve the given problem, the given sample location file was used as starting value. The library py-wake was used to generate wake field. The given Farm_evaluator_vecc file was reconstructed for taking input an array of dimension 100, and used as cost function for a minimization problem. The return value of  Farm_evaluator_vecc was inverted.

#### Methods used for Minimization-
    • Particle Swarm Optimization using PySwarm[1]
    • Scipy Optimizer- “nelder-mead”[2]
    • Genetic Algorithm Using PyGAD and GeneticAlgorithm Libraries[3]
    • Simulated Annealing Using Mlrose library[4]
    • Random Hill Climb/Hill Climb Using Mlrose library[5]

In initial stages of Optimization Particle Swarm was used to optimize the cost function with initail value set to Turbine_loc_test as initial value. With over ~50,000 iterations, the Average Energy Production improved from ~505 Gwh to ~520 Gwh. At this stage net increase in gain from Particle Swarm decreased, possible stagnation in local minima. To further optimize the cost function, A combination of Scipy Optimizer and Particle Swarm was used, with each taking the output of the other as initial value. This followed for over ~10,000 iterations with increase in Energy to ~530GWh. 
With no more improvement from Particle Swarm, Scipy Optimizer was singularly run with over ~30,000 iterations, which increased Average Power from ~530GWh, to ~535GWh. No further progress was made using Scipy Optimizer. An increase of  ~1GWh was done using Hill Climb method in Mlrose library in python.
![Alt Text](https://github.com/Bhavya1705/WindFarmOptimization/blob/main/growth.png)
Fig.1. Change in Energy V/S CSV Files Created
![Alt Text](https://github.com/Bhavya1705/WindFarmOptimization/blob/main/11.png)
![Alt Text](https://github.com/Bhavya1705/WindFarmOptimization/blob/main/21.png)
Fig.2. Visualization using Py-Wake
![Alt Text](https://github.com/Bhavya1705/WindFarmOptimization/blob/main/placement.png)
Fig.3. Placement of Tuebines
#### Other Techniques used:
    • Wind farm layout optimization problem (WFLOP) SUGGA Python toolbox
      (https://github.com/JuXinglong/WFLOP_SUGGA_Python) -Allows for broad level Optimization, does not do changes locally.

#### References
    1. https://docs.scipy.org/doc/scipy/reference/optimize.minimize-neldermead.html#optimize-minimize-neldermead
    2. https://mlrose.readthedocs.io/en/stable/source/tutorial1.html
    3. https://pyswarms.readthedocs.io/en/latest/
    4. https://pygad.readthedocs.io/en/latest/
    5. https://pypi.org/project/geneticalgorithm/
    6. https://topfarm.pages.windenergy.dtu.dk/PyWake/notebooks/Quickstart.html
    7. https://github.com/JuXinglong/WFLOP_SUGGA_Python)
###### Material that require Looking into
    1. https://github.com/byuflowlab/PlantEnergy
    2. https://github.com/sohailrreddy/WindFLO
