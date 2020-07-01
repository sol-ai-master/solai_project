# solai_project

This is the code for the character generation system presented in the master thesis
"Evolutionary algorithms for generating interesting fighting game character mechanics" by by Skjærseth and Vinje (2020).

This repository links to three other repositories.
- "sol_champ" containes the code for the Sol fighting game
- "solai_game_simulator" containes the code for the simulation based feasibility evaluator.
- "solai_evolutionary_algorithm" containes the code for the Constrained Novelty Search algorithm. The parameters for this algorithm are set in the code.

The system runs fine on windows, but might have problems on osx and linux

## Setup

To run the system, some dependencies are needed:
- Java 11
- Python 3.8
- pipenv
- Redis server (can be found here: https://redis.io/)

To clone all three repositories, run the command
```
git clone --recurse-submodules https://github.com/sol-ai-master/solai_project.git
```


## Run the system

Start the redis server, and let it listen at the default port (port 6379)
```
redis-server
```

Start the game simulator
```
cd solai_game_simulator
./gradlew bootRun
```
The game simulator is a service that connects to the redis server, and waits for simulation requests.


Setup and start the evolutionary algorithm
```
cd ../solai_evolutionary_algorithm
```
Configurations can be made in the file: solai_evolutionary_algorithm/solai_evolutionary_algorithm/main.py

Start the system by:
```
pipenv run python -m solai_evolutionary_algorithm
```

The algorithm connects to the redis-server and pushes simulations.
During the research, the algorithm pushed characters to a database. The database is not accessible to the public, such that characters are discarded after a run.


Contact the developers if you want to get in touch or get a further introduction to the system:
- Eirik H. Skjærseth: eirik1502@gmail.com
- Harald Vinje: 
            
