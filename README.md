# Harmonic Integration via Randomized Kaczmarz Algorithms

This code is part of the paper: "[On the Conjugate Symmetry and Sparsity of the Harmonic Decomposition of Parametric Surfaces with the Randomised Kaczmarz Method](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4365845)". We here used the randomized Kaczmarz algorithm to integrate harmonic functions that can be found sparse and have conjugate symmetry properties into them. This code is available under the GNU license. 

The following interfaces have been proposed in our paper:
RK: is the standard Randomized Kaczmar (RK) method and we apply it as is without modifications.

RK_conjugate_symmetry: is the newly modified approach (see the paper) where we take into account solving for zero- and positive-order only. While for negative orders we make use of the conjugate symmetry and map them linearly from assuming the knowledge of the positive ones.

RK_sparse: is a solver that uses the standard sparse approach assuming that the linear system is supported on large harmonics where they account for a significant reduction of the least-squares error. This solver is provided as is from the literature without modifications.

RK_sparse_conj_sym: is the same sparse solver, but taking into account the conjugate symmetry to reduce the dimensionality of the sparse problem.

RK_assembly: is a solver that combines two solvers: (i) RK_sparse_conj_sym to provide good initial solutions; and (ii) RK_conjugate_symmetry as a second stage for the solution where we assume back that the system is dense while using the conjugate symmetry.

Finally, for classical least-squares L1 and L2-norm solvers, we implemented some of them in the 'harmonic_helper.py'. The users can use these algorithms for comparisons.

The dataset where the analysis results of this paper were based, is published on [Zenodo](https://zenodo.org/record/8118265).
