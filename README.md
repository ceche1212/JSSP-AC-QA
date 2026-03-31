# Quantum Annealing Heuristics for the Job Shop Scheduling Problem with Availability Constraints

This repository contains the data and code accompanying the paper:

**Quantum Annealing Heuristics for the Job Shop Scheduling Problem with
Availability Constraints**


## Instance format

Instances are provided in the format **instance.jspmu** .Each instance follows a simple text format. The first line contains the
number of jobs and machines. The following lines describe the operations
of each job as pairs *(machine, processing time)* listed in processing
order.

After the job descriptions, machine unavailability periods are specified
in a dedicated section called `[MACHINE_HOLES]`.

Each machine entry contains: - Machine index - Number of unavailability
periods - For each unavailability: start time and duration

If the start time of an unavailability is not fixed (variable position),
it is indicated with **-1**.

### Example instance

    3 3
    0 3 1 2 2 3
    0 2 2 1 2 2
    2 2 0 3 2 2

    [MACHINE_HOLES]
    0 2 0 1 1 1
    1 2 1 1 2 1
    2 2 1 1 2 1

### Interpretation

-   **3 3** → 3 jobs and 3 machines
-   Each of the next three lines describes one job
-   Example: `0 3 1 2 2 3` means:
    -   Operation 1: machine 0, duration 3
    -   Operation 2: machine 1, duration 2
    -   Operation 3: machine 2, duration 3

Machine holes section:

Example: `0 2 0 1 1 1`

Means: - Machine 0 - 2 unavailability periods - Hole 1: start 0,
duration 1 - Hole 2: start 1, duration 1

## Description of contents

### Literature benchmark instances

The folder `Instances/` contains the 23 Job Shop Scheduling
benchmark instances modified to include machine availability
constraints.

These instances are used for: - Benchmarking the proposed heuristic -
Comparison with classical dispatching rules - Evaluation against optimal
references

### Embedding analysis instances

The folder `Re-scaled-Instances/` contains downsized and rescaled
instances used to study:

-   QUBO size growth
-   Minor embedding feasibility
-   Hardware limitations of quantum annealers

### Notebooks

The `notebooks/` directory contains the Jupyter notebooks used to
generate the numerical results of the paper.

### Results

The `Code/` folder contains raw numerical outputs used to generate
the tables and figures.

## Reproducibility

To reproduce the experiments:

1.  Install required Python dependencies
2.  Load the provided instances
3.  Run the notebooks in the notebooks directory

## Citation

If you use this repository, please cite the associated paper. Reference
information will be added after publication.

## Contact

For questions, please open a repository issue.
