# Description

This Project is an implementation of Diem Byzantine Fault Tolerance (DiemBFT) algorithmic core and discusses the consensus protocol which is responsible for forming agreement on ordering and finalizing transactions among a configurable set of validators.


# Platform

DistAlgo version - 1.1.0b15
Python implementation - CPython
Python version - 3.7.10

## Workload generation

Client workload distribution is being generated in `test_suite.py`. We are generating the list of client messages per node-id with seperate configurable parameters. This file can be modified to include more test cases or modify existing test cases as ncesseary. There are also hyperparameteres present within the `main.da` file which control the main configurable parameters.

## Timeouts

Local timeouts - Local timeouts within nodes generating timeout messages with timeout information, last round timeout certificate (if present), high commit QC (highest QC that serves as a commit certificate), Pacemaker maintains round times in order to advance rounds and maintains liveness. Generates TC if conditions are met. 

## Main files

 - main.da - contains code for the main module for clients & replicas. Also includes initialization parameters. 
 - blockTree.da - contains module that generates proposal blocks. It keeps track of a tree of blocks pending commitment with votes and QC’s on them.
 - safety.da - contains module that implements the core consensus safety rules.
 - pacemaker.da - contains module that maintains the liveness and advances rounds.
 - mempool.da - contains module that provides transactions to the leader when generating proposals.
 - leaderElection.da - contains module that maps rounds to leaders and achieves optimal leader utilization under static crash faults while maintaining chain quality under Byzantine faults.
 - ledger.da - contains module that creates ledger represenations and stores/updates within the path. 

## Language feature usage

- List comprehensions - 5
- Dictionary comprehensions - 3
- Await statements - Awaiting until expression becomes true or has a timeout after T seconds. 1
- Receive handlers - Used to receive messages and act upon by topic. 1

