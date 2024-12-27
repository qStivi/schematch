# Structural Schema Matching with Similarity Flooding

This project is a fork of the [schematch project](https://github.com/avielhauer/schematch), developed by the **Big Data Analytics Group** at the University of Marburg. It implements the **Similarity Flooding (SF) algorithm** by Melnik et al., as described in this [conference paper](https://old.dbs.uni-leipzig.de/file/icde2002-sf.pdf).

## Enhancements for Bachelor Thesis

In the context of my Bachelor Thesis, *"Structural Schema Matching with Similarity Flooding"*, additional methods were developed to incorporate dependency information (functional dependencies, unique column combinations & inclusion dependencies) into the SF algorithm. These enhancements aim to extend the algorithm's capabilities and improve schema matching performance.

## Usage

To use the enhanced methods described in the thesis, add the following configuration to your `first_line_matcher.yaml` file:

```yaml
name: "SimilarityFlooding"
packageName: "similarityFlooding"
params:
  wholeSchema: ["true", "false"] 
  propCoeffPolicy: ["INV_PROD", "INV_AVG"] # Propagation Coefficient Policy: Inverse Product or Inverse Average
  fixpoint: ["BASIC", "A", "B", "C", "BASIC_Lambda", "A_Lambda", "B_Lambda", "C_Lambda"] # Fixpoint Formula: Basic, A, B, or C; or Lambda adaptations
  eps: ["0.0001"] # Precision of convergence
  maxIter: ["100"] # Maximum number of iterations
  FDV1: ["true"] # FD-Quick Graph Extension
  FDV2: ["false"] # FD-Complete Graph Extension
  UCCV1: ["true"] # UCC-Quick Graph Extension
  UCCV2: ["false"] # UCC-Complete Graph Extension
  INDV1: ["true"] # IND-Quick Graph Extension
  INDV2: ["false"] # IND-Complete Graph Extension
  FDSim: ["0.0"] # Initial similarities for FD-Dependency-ID nodes
  UCCSim: ["0.0"] # Initial similarities for UCC-Dependency-ID nodes
  INDSim: ["0.0"] # Initial similarities for IND-Dependency-ID nodes
```

## Documentation

For a general manual on using the schematch project, along with links to additional large datasets, refer to the official [wiki](https://github.com/avielhauer/schematch/wiki).
