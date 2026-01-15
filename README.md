# DCCBS
This code was developed based on the work of Li [1] and Shen [2].
 
 
## Usage
The code requires the external library [boost](https://www.boost.org/). 
If you are using Ubuntu, you can install it simply by
```shell script
sudo apt install libboost-all-dev
``` 
Another easy way of installing the boost library is to install anaconda/miniconda and then 
```shell script
conda install -c anaconda libboost
```
which works for a variety of [systems](https://anaconda.org/anaconda/libboost)
(including linux, osx, and win).

If neither of the above method works, you can also follow the instructions 
on the [boost](https://www.boost.org/) website and install it manually.


After you installed boost and downloaded the source code, go into the directory of the source code and compile it with CMake: 
```shell script
cmake -DCMAKE_BUILD_TYPE=RELEASE .
make
```

Then, you are able to run the code:
```shell script
./cbs -m lak303d.map -a lak303d-even-20.scen -k 51 -t 60 --cluster_heuristic=DCCBS -h 2 -p 1000 -r 0 -l 0
```

- m: the map file from the MAPF benchmark
- a: the scenario file from the MAPF benchmark
- o: the output file that contains the search statistics
- outputPaths: the output file that contains the paths 
- k: the number of agents
- t: runtime limit (in seconds)
- cluster_heuristic: cluster heuristic method
- h: search range
- p: search decaying period
- r: search decaying rate
- l: minimum search range

## References
[1] Jiaoyang Li, Daniel Harabor, Peter J. Stuckey, and Sven Koenig. Pairwise Symmetry Reasoning for Multi-Agent Path Finding Search. Artificial Intelligence, 301: 103574, 2021.

[2] Shen, Bojie, Zhe Chen, Jiaoyang Li, Muhammad Aamir Cheema, Daniel D. Harabor, and Peter J. Stuckey. Beyond pairwise reasoning in multi-agent path finding. In Proceedings of the International Conference on Automated Planning and Scheduling, vol. 33, pp. 384-392. 2023.
