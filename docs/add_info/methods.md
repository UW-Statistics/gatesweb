---
hide:
    - toc
---

# Methods
---
The results contained here are based on Demographic Health Surveys (DHS). DHS data are collected using a stratified two-stage cluster sampling design and this sampling must be taken into account when we produce estimates. This can be achieved by using <a href="https://sae4health.stat.uw.edu/method/method_direct/" target="_blank">weighted estimation</a>. This generally works well for the first geographical administrative level (so-called Admin-1), since DHS surveys are powered to produce reliable estimates at Admin-1. For the second administrative level (Admin-2), data sparsity becomes an issue and so we use the most popular small area estimation (SAE) approach, which is the <a href="https://sae4health.stat.uw.edu/method/method_area/" target="_blank">Fay-Herriot model</a>. Under this model, the weighted estimates are smoothed over space, which increases the precision of estimation (reduces uncertainty) in each constituent area, because the data from neighboring areas are aiding in the estimation.

The Fay-Herriot model needs two inputs for each area: a weighted estimate and its variance. At Admin-2, sparse data can make the design-based variance zero or undefined, and the area then can’t be used in the model. Two common cases cause this: a stratum (urban or rural) within the area has only one sampled cluster, or every sampled cluster in the area gives the same estimate (for example, no cases were observed). To handle these areas we apply an <a href="https://arxiv.org/abs/2602.14387" target="_blank">automatic variance adjustment</a> (the “variance fix”). It adds a “phantom” cluster to each affected stratum, as if it came from a hypothetical prior survey. The phantom cluster’s prevalence is the national weighted estimate for that stratum (urban or rural), and its weight is the national average survey weight of clusters in that stratum. The weighted estimate and its variance are then recalculated on this augmented sample, using the same design-based formula as for the real data. The adjusted estimate is a weighted average of the area’s own data and the national stratum-level value. Its variance is positive and reflects how little data the area has. The fix is applied only where the standard formula fails. Areas with an adequate variance estimate are left unchanged.

We include maps of point estimates, and of the uncertainty, measured through the width of a 90% uncertainty interval. Ridge plots show the complete uncertainty distribution associated with prevalence estimation. On the point estimation maps, areas with high uncertainty have hatching. On the uncertainty width maps, areas with sparse data may yield ill-defined uncertainty, and these are colored gray.
---

# Developers
---
This website was developed by researchers at the University of Washington and the University of California Santa Cruz, with support from the Gates Foundation.