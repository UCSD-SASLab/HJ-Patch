# Patching Neural Barrier Functions with HJ Reachability

This repository contains the implementation of `HJ-Patch` accompanying the paper [Patching Neural Barrier Functions using Hamilton-Jacobi Reachability](https://github.com/UCSD-SASLab/HJ-Patch/blob/main/paper.pdf) by Sander Tonkens, Alex Toofanian, Zhizhen Qin, Sicun Gao, and Sylvia Herbert, submitted to IEEE Conference on Decision and Control (CDC), 2023

This project locally patches almost-barrier functions to guarantee safety, providing a 10-100x speedup over using vanilla HJ reachability


## Requirements

- `hj_reachability` package: https://github.com/toofanian/hj_reachability. Custom fork that accepts an ``active'' region to be updated (although no speed up)
- `optimized_dp` package: https://github.com/toofanian/optimized_dp. Custom fork that accepts an ``active'' region and has a speedup from only computing on subset of states
- `cbf_opt` package: https://github.com/stonkens/cbf_opt
- For post-hoc analysis: `experiment_wrapper` package: https://github.com/stonkens/experiment_wrapper


## Installation

Install all requirements and its dependencies using `pip install -e .` in your local conda environment. Then clone this repository and run `pip install -e .`

## Usage
- `refineNCBF` contains all source code for interfacing with the `optimized_dp` and the `hj_reachability` solvers. Contains the `HJ-Patch` and vanilla HJ reachability implementations and a wide variety of implementation possibilities (different expansion methods, different breaking conditions, etc.)
- `scripts`: Contains codes that were used for generating the results in the paper
- `data`: Contains all the data functions (lfs will be added at a later stage)
