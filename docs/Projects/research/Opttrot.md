---
layout: post
title: OptTrot and Tensorized Pauli Composer
nav_order: 1
parent: Research
has_children: false
permalink: /docs/projects/research/opttrot
description: "Algorithms and software for Pauli operators and Trotterized quantum circuits"
---

# OptTrot and Tensorized Pauli Composer

These projects develop efficient representations and computational routines for Pauli operators, Hamiltonian matrices, and Trotterized quantum circuits.

## Tensorized Pauli Composer

Tensorized Pauli Composer constructs Hamiltonian matrices from weighted Pauli polynomials. The method combines symplectic representations of Pauli elements with inverse tensorized Pauli decomposition.

My contributions include independent algorithm design, implementation, benchmark development, and integration into the broader OptTrot project. The work was presented as a poster at Quantum Threads 2024.

[Source code](https://github.com/OptTrot/Tensorized-Pauli-Composer){: .btn .mr-2 }
[Technical preprint](https://doi.org/10.5281/zenodo.14245728){: .btn .mr-2 }

## OptTrot

OptTrot is a research software project for efficiently manipulating Pauli elements and constructing shorter Trotterized circuits for Hamiltonian simulation.

Selected components include:

- bit-string and symplectic Pauli representations implemented in C;
- Pauli-group algebra and Pauli-polynomial manipulation;
- Hamiltonian decomposition and operator conversion;
- Trotter-circuit generation and optimization interfaces.

In the reported 12-qubit Pauli-polynomial matrix-construction benchmark, the OptTrot implementation completed in 3.48 seconds compared with 33.2 seconds for Qiskit in the same test configuration.

[OptTrot repository](https://github.com/OptTrot/OptTrot){: .btn .mr-2 }
