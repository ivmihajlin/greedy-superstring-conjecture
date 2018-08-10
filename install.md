# Deployment

Here we describe how to deploy this webpage and the required applications on a machine without sudo permissions.

## Installing Concorde on a Linux Machine

In order to find an optimal solution to the Shortest Common Superstring problem (SCS), we use the [**Concorde** Traveling Salesman Solver](http://www.math.uwaterloo.ca/tsp/concorde.html).

First we download the [**QSopt** Linear Programming Solver](https://www.math.uwaterloo.ca/~bico/qsopt/).

	mkdir qsopt
    cd qsopt
    wget http://www.math.uwaterloo.ca/~bico//qsopt/beta/codes/linux64/qsopt{.h,.a,}
    QSOPT_PATH=$PWD;
    
Now we're ready to download and install **Concorde**.

	cd ..
    wget http://www.math.uwaterloo.ca/tsp/concorde/downloads/codes/src/co031219.tgz
    tar xf co031219.tgz
    cd concorde
    ./configure --with-qsopt=$QSOPT_PATH
    make

In order to test the solver, we can run the following commands.

	cd TSP
    wget https://wwwproxy.iwr.uni-heidelberg.de/groups/comopt/software/TSPLIB95/tsp/a280.tsp.gz
    gunzip a280.tsp.gz
    ./concorde a280.tsp
    
   
## Installing Pygraphviz on a Linux Machine
	npm install graphviz
	python3 -m pip install setuptools --user
	python3 -m pip install pygraphviz --user --install-option="--include-path=/usr/include/graphviz" --install-option="--library-path=/usr/lib/graphviz/" 


## Installing Flask on a Linux Machine

Just run one of the following commands (depending on your package manager):
	
    npm install Flask
    sudo apt-get install Flask
    sudo pip install Flask
    sudo pip3 install Flask

For ease of running Flask install the python-dotenv package

    pip install python-dotenv