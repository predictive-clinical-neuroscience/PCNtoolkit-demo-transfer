# PCNtoolkit demo: transfer a pretrained normative model

Material from the PCNtoolkit hands-on at the [Donders (f)MRI Toolkit](https://www.ru.nl/en/donders-institute/agenda/donders-fmri-toolkit), 20 November 2026.

| | |
|---|---|
| **Web app** | [Fit or transfer on a small dataset](https://predictive-clinical-neuroscience.github.io/PCNtoolkit-demo-transfer/): change the number of controls (5–60) and the adaptation/test split, switch between fit and transfer |
| **Notebook** | [`notebooks/transfer_icbm.ipynb`](notebooks/transfer_icbm.ipynb) · [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/predictive-clinical-neuroscience/PCNtoolkit-demo-transfer/blob/main/notebooks/transfer_icbm.ipynb) |
| **Slides** | [`slides/`](slides/) (PDF, including the PCNportal walkthrough) |
| **Data** | [`data/icbm_fcon1000.csv`](data/icbm_fcon1000.csv): the 85 ICBM participants, all FreeSurfer measures |
| **PCNportal files** | [`data/pcnportal/`](data/pcnportal/): the same 20 controls (adaptation) and 65 test participants, in PCNportal's template format |

## Cite and reuse

- PCNtoolkit: see [CITATION.cff](https://github.com/predictive-clinical-neuroscience/PCNtoolkit/blob/main/CITATION.cff) in the PCNtoolkit repo.
- Pretrained lifespan models: the approach is described in Rutherford et al. (2022), *eLife*, [doi:10.7554/eLife.72904](https://doi.org/10.7554/eLife.72904); cite the reference given with the specific model you use.
- PCNportal: Barkema et al. (2023), *Wellcome Open Research*, [doi:10.12688/wellcomeopenres.19591.2](https://doi.org/10.12688/wellcomeopenres.19591.2).
- Data: [FCON1000](https://fcon_1000.projects.nitrc.org/fcpClassic/FcpTable.html), ICBM site (A.C. Evans), released openly by the 1000 Functional Connectomes Project; derived FreeSurfer measures as distributed with PCNtoolkit.
- This material: see [CITATION.cff](CITATION.cff). Code is GPL-3.0 (as PCNtoolkit, see [LICENSE](LICENSE)); slides and text are CC BY 4.0.

Questions: [NeuroStars, tag pcntoolkit](https://neurostars.org/tag/pcntoolkit) · [PCNtoolkit issues](https://github.com/predictive-clinical-neuroscience/PCNtoolkit/issues)
