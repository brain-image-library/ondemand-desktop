Interactive Desktop Configuration for BIL Cluster
This repository contains a YAML configuration file (interactive_desktop.yml) for launching an interactive Xfce desktop environment on the Brain Image Library (BIL) cluster, designed for compute-intensive tasks such as brain imaging analysis.
Overview
The YAML file defines a form-based interface for configuring a Slurm job to run an interactive desktop session on the BIL cluster. Users can specify parameters like CPU cores, memory allocation, session duration, and other Slurm options to tailor the session to their needs.
YAML File Structure
The configuration file includes the following key sections:

Title and Cluster: Specifies the application name (Interactive Desktop) and the target cluster (bil).
Description: Briefly describes the application as launching an Xfce desktop for compute-intensive tasks like brain imaging analysis.
Form: Lists the input fields for the user interface, including:
bc_vnc_idle
desktop
bc_account
bc_num_hours
bc_num_slots
bc_num_cores
bc_memory
node_type
bc_queue
bc_vnc_resolution
extra_slurm_args
bc_email_on_started


Attributes: Defines the properties and constraints for key fields, such as:
desktop: Selects the Xfce desktop environment.
bc_num_cores: Sets 4–64 CPU cores (steps of 1, default: 4).
bc_num_hours: Sets 1–8 hours for session duration (steps of 1, default: 1).
bc_memory: Allocates 8–2900 GB of memory (steps of 1, default: 8).
Other fields like bc_vnc_resolution (required), bc_queue (default: "applications"), and extra_slurm_args.


Submit: Points to a Slurm submission script (submit/submit.yml.erb).

Key Parameters

Desktop Environment: Fixed to Xfce, optimized for HPC performance.
Number of Cores: Configurable from 4 to 64 cores to balance performance and resource usage.
Session Duration: Adjustable from 1 to 8 hours to suit task requirements.
Memory Allocation: Ranges from 8 GB to 2900 GB for resource-intensive applications like brain imaging analysis.
VNC Resolution: Must be specified by the user for the desktop display.
Extra Slurm Args: Allows additional Slurm parameters for advanced customization.

Usage

Clone this repository to your local environment or cluster.
Ensure the BIL cluster environment supports the Slurm workload manager and Xfce desktop.
Modify the YAML file if needed (e.g., adjust defaults or constraints).
Use the YAML configuration with a compatible job submission system (e.g., Open OnDemand) to launch the desktop session.
Configure parameters via the form interface to allocate resources and start the session.

Notes

Ensure resource allocations (cores, memory, hours) are appropriate to avoid overloading the cluster.
The bc_vnc_resolution field is mandatory and must be set before submission.
For advanced Slurm configurations, use the extra_slurm_args field.

---
Copyright © 2025 Pittsburgh Supercomputing Center. All Rights Reserved.

The [Biomedical Applications Group](https://www.psc.edu/biomedical-applications/) at the [Pittsburgh Supercomputing Center](http://www.psc.edu) in the [Mellon College of Science](https://www.cmu.edu/mcs/) at [Carnegie Mellon University](http://www.cmu.edu).
