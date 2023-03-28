Results of ALiCT
=================

## Table of Contents
   * [Results of ALiCT](#results-of-alict)
      * [Table of Contents](#table-of-contents)
      * [Linguistic Capability Specifications](#linguistic-capability-specifications)
      * [Experiment Results](#experiment-results)
         * [RQ1: Diversity](#rq1-diversity)
         * [RQ2: Effectiveness](#rq2-effectiveness)
         * [RQ3: Consistency](#rq3-consistency)
<!-- 
You can find more results at the project site(https://sites.google.com/view/s2lct/home). -->


## Linguistic Capability Specifications
<div align="center">
    <span style="font-size:1.5em">
        <strong>Table 1: Search predicates for ten linguistic capabilities of sentiment analysis.</strong>
    </span>
</div>
<p align="center">
    <img src="./tables/lc-spec-table.png" alt="lc-spec-table" width=auto height=auto title="lc_spec_table">
</p>

<div align="center">
    <span style="font-size:1.5em">
        <strong>Table 2: Search predicates for ten linguistic capabilities of hate speech detection.</strong>
    </span>
</div>
<p align="center">
    <img src="./tables/hsd-lc-spec-table.png" alt="hsd-lc-spec-table" width=auto height=auto title="hsd_lc_spec_table">
</p>

## Baselines
### Capability Testing Baselines
ALiCT is evaluated by comparing with the state-of-the-art linguistic capability testing for sentiment analysis and hate speech detection as following:

> 1. CHECKLIST([paper](https://homes.cs.washington.edu/~marcotcr/acl20_checklist.pdf), [repo](https://github.com/marcotcr/checklist)) for sentiment analysis
> 2. Hatecheck([paper](https://aclanthology.org/2021.acl-long.4/), [repo](https://github.com/paul-rottger/hatecheck-data)) for hate speech detection

### Model Under Test
Given the generated test cases from the ALiCT and [capability testing baselines](#capability-testing), models in the table 3 are evaluated:
<div align="center">
    <span style="font-size:1.5em">
        <strong>Table 3: The NLP model used in our evaluation.</strong>
    </span>
</div>
<p align="center">
    <img src="./tables/model-under-test.png" alt="lc-spec-table" width=auto height=auto title="lc_spec_table">
</p>

### Evaluation of of expansion phase of ALiCT
the test case diversity provided by ALiCT expansion phase of ALiCT is also compared against that of one syntax-based (MT-NLP) and three adversarial (Alzantot-attack, BERT-Attack and SememePSO-attack) as follows:

- Syntax-based approach
> MT-NLP: [Metamorphic Testing and Certified Mitigation of Fairness Violations in NLP Models](https://www.ijcai.org/Proceedings/2020/64)

- Adversarial approaches
> Alzantot-attack: [Generating Natural Language Adversarial Examples](https://aclanthology.org/D18-1316/)   
> BERT-Attack: [BERT-ATTACK: Adversarial Attack Against BERT Using BERT](https://arxiv.org/abs/2004.09984)  
> SememePSO-attack: [Word-level textual adversarial attacking as combinatorial optimization](https://arxiv.org/abs/1910.12196)



## Experiment Results
### RQ1: Diversity

### RQ2: Effectiveness

### RQ3: Consistency
