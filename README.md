# phys7101_2026_resources

**Course materials for the Lancaster University module PHYS7101 "Numerical Methods and Data Analysis": 2026/2027**

Course convenors: Mat Smith (mat.smith@lancaster.ac.uk) and Aneta Stefanovska (aneta@lancaster.ac.uk)

***

This module introduces key techniques in numerical methods and data analysis used across physics and industry. Each week has introductory lectures and a practical session in Python, using real datasets wherever possible.

## Topics

| Week | Topic |
| --- | --- |
| 1 | Introduction; Numerical Computation and Simulation |
| 2 | Root-Finding, Parameter Estimation and Optimisation |
| 3 | Interpolation, Extrapolation, Differentiation and Integration |
| 4 | Error Propagation, Hypothesis Testing and Time-Series Analysis |
| 5 | Uncertainty, Random Processes and Monte Carlo Methods |
| 6 | Numerical Linear Algebra and Clustering |
| 7 | Bayesian Inference, Posterior Distributions and MCMC |
| 8 | Classification and Optimisation |
| 9 | Method Selection |
| 10 | Neural Networks and Scientific Data Analysis |

## Assessment

| Component | Coverage | Weight |
| --- | --- | --- |
| Exercise 1 | Weeks 1–3 | 25% |
| Exercise 2 | Weeks 4–6 | 25% |
| Exercise 3 | Weeks 7–10 | 40% |
| In-class assessment | Weeks 6–7 and 8–9 | 10% |

Deadlines and submission links are on Moodle. Exercises 1 and 2 are each submitted as an already-run, annotated Jupyter notebook and a short interpretive statement (max. 300 words). Exercise 3 is an annotated notebook and a 5-page report covering the problem, the methodology, the key results and what they mean. Every submission also needs the mandatory GenAI-usage declaration. See `workshops/week1/week1_setup.ipynb` for details.

## Using these notebooks

Everything runs in [Google Colab](https://colab.research.google.com/): click an **Open in Colab** badge below, then immediately use **File → Save a copy in Drive** so your work is kept. Each notebook loads its data directly from this repository, so nothing needs to be downloaded.

To work locally instead, clone or download the whole repository; the notebooks will then read data from each week's `datasets/` folder.

## Logbook

Keep one logbook for the whole module, starting in Week 1. The recommended format is a Google Doc: **[make your own copy of the template](https://docs.google.com/document/d/1sATUC_XWqk_ZO6NPm3LnXH4TAN1N3lxo4Oj86kBlJVs/copy)**. You're welcome to adapt it to another format; there are also [Word/OneNote](logbook/logbook_template.docx) and [notebook](https://colab.research.google.com/github/MatSmithAstro/phys7101_2026_resources/blob/main/logbook/logbook_template.ipynb) versions. See Section 6 of `week1_setup.ipynb` for what it should contain.

## Week 1 workshop

Work through these in order:

| Notebook | Content | |
| --- | --- | --- |
| `week1_setup.ipynb` | Start here: Colab, notebooks, Markdown, logbooks, submitting work, GenAI | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MatSmithAstro/phys7101_2026_resources/blob/main/workshops/week1/week1_setup.ipynb) |
| `week1_tidal_hook.ipynb` | Is this signal or noise? Real Lancaster Quay tidal data; describing data and distributions | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MatSmithAstro/phys7101_2026_resources/blob/main/workshops/week1/week1_tidal_hook.ipynb) |
| `week1_revision.ipynb` | NumPy, pandas and Matplotlib refresher | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MatSmithAstro/phys7101_2026_resources/blob/main/workshops/week1/week1_revision.ipynb) |
| `week1_foundations.ipynb` | Floating-point error, catastrophic cancellation, algorithmic complexity; take-home exercise | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MatSmithAstro/phys7101_2026_resources/blob/main/workshops/week1/week1_foundations.ipynb) |
| `week1_euler_rk4_lab.ipynb` | Euler vs RK4: which one do you trust? | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MatSmithAstro/phys7101_2026_resources/blob/main/workshops/week1/week1_euler_rk4_lab.ipynb) |
