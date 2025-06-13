## Code Overview
Below are the files included in this artifact:

```
all.cfg                                     - Collects all Beluga source files
1_definitions.bel                           - Contains encoding of syntax, semantics and dependency relations for CCSKP
2_basic_properties.bel,                     - Contains basic properties of keys, proof keyed labels and transitions
3_lemmas_connectivity_relationship_one.bel  - Proof of auxiliary lemmas for Theorem 2.1(i)
4_connectivity_relationship_one.bel         - Proof of Theorem 2.1(i)
5_lemmas_connectivity_relationship_two.bel  - Proof of auxiliary lemmas for Theorem 2.1(ii)
6_connectivity_relationship_two.bel         - Proof of Theorem 2.1(ii)
7_complementarity.bel                       - Proof of Theorem 2.6 (complementarity of dependence and independence)
```
Remarks:

- Most of the results proved in the file `2_basic_properties.bel` are technical lemmas which are essential for the encoding, despite being taken for granted in the informal discussion of the system. For example, while it is clear that each proof keyed label has a unique key and label, this result needs to be explicitly proved in the Beluga formalization.
- The main results in this work are Theorems 2.1 and 2.6. Although the paper states Lemmas 2.2 and 2.3 to prove the former, it is further explained that the two lemmas are not required in the encoding. For this reason, their encoding is not present in this artifact.

## Paper-to-Artifact Table
The following table pairs up definitions and proofs from the paper with those from the Beluga code.

| Definitions/Proofs                                       | Paper         | File                                | Name of the encoding           |
|----------------------------------------------------------|---------------|-------------------------------------|--------------------------------|
| Names, keys, labels, processes                           | Section 2.1   | 1_definitions.bel                   | names, keys, labels, proc      |
| Standard processes                                       | Section 2.1   | 1_definitions.bel                   | std                            |
| Proof keyed labels; label and key of a proof keyed label | Section 2.2   | 1_definitions.bel                   | pr_lab, lab, key               |
| Forward, backward, combined transitions                  | Section 2.2   | 1_definitions.bel                   | fstep, bstep, step             |
| Paths, connected transitions, reachable processes        | Section 2.3   | 1_definitions.bel                   | step*, conn_tr, reachable      |
| Loop lemma                                               | Section 2.3   | 2_basic_properties.bel              | loop_lemma_one, loop_lemma_two |
| Connectivity, dependence, independence of proof labels   | Section 2.3   | 1_definitions.bel                   | conn, dep, indep               |
| Theorem 2.1 (i)                                          | Section 2.4   | 4_connectivity_relationship_one.bel | conn_rel_one                   |
| Theorem 2.1 (ii)                                         | Section 2.4   | 6_connectivity_relationship_two.bel | conn_rel_two                   |
| Realisation                                              | Section 2.4   | 5_lemmas_connectivity_relationship_two.bel | realised                |
| Lemma 2.5                                                | Section 2.4   | 5_lemmas_connectivity_relationship_two.bel | pr_lab_is_realised      |
| Theorem 2.6            | Section 2.4 | 7_complementarity.bel | indep_impl_conn, dep_impl_conn, conn_impl_dep_or_indep, impossible_dep_and_indep |
