# Explainable Adaptation to Concept Drift in Decision Tree Ensembles
## *UAI 2026*

Decision trees are widely used in machine learning due to their interpretability.
  However, when the underlying data distribution changes---a phenomenon known as concept drift---their performance can degrade significantly.
  Retraining the model from scratch discards the learned structure and offers no insight into which nodes were actually affected.
  Prior work, APPETITE, used spectrum-based fault localization to identify and modify a single faulty node, but cannot handle drift that affects multiple nodes simultaneously or that demands structural changes to the tree.
  We propose BTAD (Bayesian Tree Adaptation for Drift), which formalizes the Decision Tree Concept Drift Problem as a Model-Based Diagnosis task and employs BARINEL, a Bayesian algorithm that ranks multi-node fault hypotheses across the entire tree.
  For repair, BTAD applies \subfitfull, which replaces affected subtrees with new ones fitted to the post-drift distribution.
  BTAD relies on lightweight node-level statistics and requires no access to the original training data.
  Experiments show that BTAD outperforms APPETITE both in terms of recovery performance as well as the explanation. In addition, BTAD achieves accuracy recovery comparable to full retraining, which, unlike BTAD, provides no insight into the nature of the drift and requires access to the original data.

## This Repository is listed as:
- APPETITE - The BTAD algorithm, with baselines in it.
- Tester - All the files relevant to evaluate the algorithm, including configurations for each baseline diagnoser that ran.
- Data - The datasets with their descriptions.
- appendix (duplicated as results) - The results for both the drift scenario runs (experinent1=Feature-Shift, experiment2=Distribution-Edge).

## Reproduce:
To run the algorithms, all needed is:
1. Install the required packages using [the requirements file](https://github.com/yoavzelinger/BTAD/blob/main/requirements.txt).
2. Choose your desired experiment [in the tester-constatns file by DRIFT_SYNTHESIZING_VERSION value](https://github.com/yoavzelinger/BTAD/blob/main/code/Tester/TesterConstants.py#L18) (the experiment number).
3. Run test_all.py file with -d 1 argument: 
    ```
        python -m test_all.py -d 1
    ```

That's it. The results will be saved in the results folder.


[Appendix of all the datasets and corresponding results can be located here](https://github.com/yoavzelinger/BTAD/tree/main/appendix/)
    Good Luck!
