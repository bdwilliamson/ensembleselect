## Extrinsic variable selection

A first approach uses .blue1[extrinsic importance]:
1. Fit a Super Learner ensemble with $L$ candidate learners; obtain weights $\{w_\ell\}_{\ell = 1}^L$

--

2. Obtain extrinsic variable importance $v_{j,\ell}$ for each feature and learner

--

3. Obtain importance ranks $\{r_{j,\ell}\}_{j=1}^p$ within each learner $\ell$

--

4. Average the ranks across learners: $r_{j,L} := \sum_{\ell = 1}^L w_\ell r_{j,\ell}$

--

5. Select all variables such that $r_{j,L} < \kappa$ for $\kappa > 1$

--

This approach can also be embedded within .blue1[stability selection] .small[ (Meinshausen and Buhlmann (2010)) ]

--

With missing data: 
1. Use multiple imputation to create $M$ datasets
2. Select variables using each dataset
3. Select final set of variables appearing in $\pi M$ datasets for $\pi \in (0, 1)$

---

## Extrinsic variable selection

&zwj;Benefits:
* extrinsic importance easy to compute
* uses cross-validation to weight the ranks
* stability selection provides error control

--

&zwj;Drawbacks:
* may not identify all relationships
* .red[post-hoc] harmonization in missing-data contexts

---