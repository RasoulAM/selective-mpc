
# Overview
This repo contains the code our paper titled "Selective MPC: Distributed Computation of Differentially Private Key-Value Statistics"

## Setup
The controller node (which can be your computer) will run the protocol. Aside from the controller node, there are also multiple other computation nodes as well.

* Run ```0-set_up_instance.sh``` in each computation node
* Run ```1-send_keys.sh <number_of_keys>``` from controller node

## Running a protocol
* Add the source program in ```Programs/Source``` (called ```<source.mpc>``` for example)
* Put the ip addresses of the nodes in a file called ```<hosts>```
* Run ```2-send_and_compile.sh <source.mpc>```
* Run ```3-run_protocol.sh <source.mpc> <ip_file_name> <protocol_type>```

## Existing Examples
The following source files (and some corresponding input files) are available in the repository. The inputs are stored at ```Programs/Public-Input```

Mean estimation:
```
    mean_est.mpc // Mean Estimation, Variable Number of Keys
    mean_est_0.mpc // Mean Estimation for 1 key
    mean_est_1.mpc // Mean Estimation for 10 keys
    mean_est_2.mpc // Mean Estimation for 100 keys
    mean_est_3.mpc // Mean Estimation for 1000 keys
    mean_est_4.mpc // Mean Estimation for 10000 keys
    mean_est_5.mpc // Mean Estimation for 100000 keys
```

Input validation:
```
    input_validation_1.mpc // Input validation for 10 inputs
    input_validation_1.mpc // Input validation for 100 inputs
    input_validation_1.mpc // Input validation for 1000 inputs
    input_validation_1.mpc // Input validation for 10000 inputs
```

## Additional Scripts for Experiments
* Place the IP addresses of all the other nodes in ```HOSTS_ALL.example``` on the controller node
* ```host_maker.py``` generates the list of IPs for our experiments using ```HOSTS_ALL.example```
* ```run_experiments.sh``` runs the experiments required for our paper
* ```run_large_experiments.sh``` runs the multithreaded experiments required for our paper
* Variables can be changed in ```vars.sh```

## Results
Our logs from the experiments are in the ```evaluation``` directory. Interpretation of our results is done in ```evaluation/Results.ipynb```