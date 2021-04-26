# Temporal Bin Packing

Nurşen Aydın, İbrahim Muter and İlker Birbil

This repository accompanies [our
paper](https://doi.org/10.1016/j.cor.2020.104959) "Multi-objective
temporal bin packing problem: An application in cloud computing"
published in Computers & Operations Research, Volume 121, 2020,
104959, ISSN 0305-0548.

## Abstract 
Improving energy efficiency and lowering operational costs are the
main challenges faced in systems with multiple servers. One prevalent
objective in such systems is to minimize the number of servers
required to process a given set of tasks under server capacity
constraints. This objective leads to the well-known bin packing
problem. In this study, we consider a generalization of this problem
with a time dimension, where the tasks are to be performed with
predefined start and end times. This new dimension brings about new
performance considerations, one of which is the uninterrupted
utilization of servers. This study is motivated by the problem of
energy efficient assignment of virtual machines to physical servers in
a cloud computing service. We address the virtual machine placement
problem and present a binary integer programming model to develop
different assignment policies. By analyzing the structural properties
of the problem, we propose an efficient heuristic method based on
solving smaller versions of the original problem
iteratively. Moreover, we design a column generation algorithm that
yields a lower bound on the objective value, which can be utilized to
evaluate the performance of the heuristic algorithm. Our numerical
study indicates that the proposed heuristic is capable of solving
large-scale instances in a short time with small optimality gaps.

**Keywords:** Bin packing; Cloud computing; Heuristics; Exact methods;
Column generation

## Test Instances

We provide 240 problem instances. For all of the test problems, the
names of the input files are of the form cap100_n#_t#_dici_no.txt,
where cap100, n, t, di, ci and no are defined as follows:

- cap100: In all instances, we assume that the servers are identical
  and the capacity is set to Cap = 100.

- n# : the number of virtual machine requests (e.g. n50, 50 VM
  requests).

- t#: the length of the VM arrival period (e.g. t50, VMs arrive
  between time 1 and time 50).

- di: the length of requested time interval which can be considered as
      the duration of a VM request.  We define two sets for VM
      duration, denoted by dS and dL, which are randomly generated in
      intervals [10, 30] and [20, 60], respectively.  In the input
      files, dS is denoted by Sh, dL is denoted by Lon.

- ci: the requested capacity for a VM request. We define two
      parameters, namely cmin (minimum capacity demand) and cmax
      (maximum requested capacity).  We generate integer capacity
      request for a VM randomly between cmin and cmax.  In our
      experiments, we set cmin = 25 and test the models for varying
      capacity requirements by changing cmax ∈ {50,75} In the input
      files, cmax = 50 is denoted by Sm, cmax = 75 is denoted by Lr.

- no: number of the instance file. For each combination of these
  parameters, 5 instances were generated.
      
For instance, the input file "cap100_n100_t120_LonLr_1.txt" has 100 VM
requests with the length of the arrival period of 120.  The durations
of VM requests (dL) are randomly generated in intervals [20, 60] and
cmax is set to 75.

Content of the input file:

- The first line in the input files provides the number of VM requests
  and the capacity of one server.  For instance, in the input file
  "cap100_n100_t120_LonLr_1.txt" 100 100 0 0 --> 100 is the number of
  VM requests, 100 is the capacity of one server

- From the second line to the end of the file, it provides the data
  for each arrived VM request.  The first column corresponds to the VM
  number (starts with 0).  The second column is the starting time of
  the request.  The third column is the completion time of the VM
  request.  The last column corresponds to the capacity request.

  For instance, in the input file "cap100_n100_t120_LonLr_1.txt", the
	second line is given as: 0 2 51 60 --> VM no=0, the starting
	time=2, the completion time=51 and the capacity request=60.


