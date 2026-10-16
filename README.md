# Landscape Ecology Statistics

A 30-step statistics learning path for **landscape ecology research and landscape design**, built around **Python**.

Starting point: no prior statistics background. Goal: the ability to design, run, diagnose and write up a quantitative landscape analysis independently.

---

## Contents

| File | Language | What it is |
| --- | --- | --- |
| `Study_Table_CN.docx` | 中文 | 30 步学习表：阶段 / 顺序 / 学习内容 / Python 练习 |
| `Study_Guide_CN.docx` | 中文 | 30 步详解：学习内容 / 思维框架 / 应用 / 学习网站 |
| `Study_Table_EN.docx` | English | 30-step table: phase / no. / what to learn / Python practice |
| `Study_Guide_EN.docx` | English | 30-step guide: what to learn / mental model / application / resources |

**01 → 30 covers:** distributions and probability · descriptive statistics · estimation and hypothesis testing · t-tests, chi-square, ANOVA · linear regression and diagnostics · model selection (AIC/BIC) · generalized linear models · mixed-effects models · cross-validation · projections and spatial data · spatial weights · Moran's I and LISA · spatial regression (SAR/SEM/SDM) · point pattern analysis · semivariograms and kriging · landscape metrics · scale effects · ordination · clustering · diversity indices · variation partitioning · reproducing a paper · scripting and writing.

---

## The six phases

| Phase | Steps | Focus |
| --- | --- | --- |
| 1 · Foundations | 01–04 | Distributions, expectation and variance, central limit theorem, minimal calculus and linear algebra |
| 2 · Inference | 05–10 | Descriptive statistics, confidence intervals, hypothesis testing logic, t-tests, chi-square, ANOVA |
| 3 · Models | 11–16 | Regression, diagnostics, model selection, GLMs, mixed-effects models, cross-validation |
| 4 · Spatial | 17–24 | Projections, spatial weights, spatial autocorrelation, spatial regression, point patterns, kriging, landscape metrics, scale |
| 5 · Multivariate | 25–28 | Ordination, clustering, diversity indices, variation partitioning |
| 6 · Practice | 29–30 | Reproducing a published analysis, scripting the workflow, figures and writing |

---

## How to work through it

Two tracks, run in parallel rather than in sequence:

- **Theory track** — follow the statistics and probability syllabus of your programme; the goal is to be able to explain and justify a method, not merely to apply it.
- **Applied track** — implement the same concept in Python during the same week. The binding of "concept → code" is the fastest route for someone starting from zero.

**Toolchain, by phase:**

```
Phase 1–2   numpy · pandas · scipy.stats · matplotlib · seaborn
Phase 3     statsmodels · scikit-learn · patsy
Phase 4     geopandas · shapely · rasterio · rioxarray · pyproj
            libpysal · esda · spreg · pointpats · splot · giddy
            PyLandStats
```

Use a dedicated conda environment for the spatial packages — `geopandas` and `rasterio` depend on GDAL, which installs far more smoothly through conda than through pip.

---

## The one thing not to get wrong

Landscape data are **inherently spatially autocorrelated**. Adjacent sample points resemble one another not by coincidence but because a spatial process produced them. This breaks the independence assumption that ordinary t-tests and OLS regression rely on, so results can be false positives.

The practical rule: after running any non-spatial model, test the **residuals** for spatial autocorrelation with Moran's I. If it is significant, use a spatial model instead. This is also one of the most common reasons landscape ecology manuscripts are rejected.

Two more worth remembering: check the **projection** before any distance or area calculation (degrees are not metres), and report **effect sizes** alongside p-values.

---

## Where the learning resources are

Every step in the two detailed guides links to 2–3 resources — free textbooks, official documentation, interactive visualisations and video courses. All links were verified as reachable. Highlights include *Geographic Data Science with Python*, *An Introduction to Statistical Learning* (ISLP), *Learning Statistics with Python*, Seeing Theory, and the PySAL documentation.

---

## Notes

The guides reflect one person's study plan, not a curriculum. The Chinese and English versions are parallel translations of the same content. Corrections, additions and alternative resource suggestions are welcome.
