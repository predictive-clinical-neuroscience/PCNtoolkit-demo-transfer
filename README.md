# PCNtoolkit demo: transfer a pretrained normative model

Material from the PCNtoolkit hands-on at the [Donders (f)MRI Toolkit](https://www.ru.nl/en/donders-institute/agenda/donders-fmri-toolkit), 20 November 2026.

| | |
|---|---|
| **Web app** | [Fit or transfer on a small dataset](https://predictive-clinical-neuroscience.github.io/PCNtoolkit-demo-transfer/): change the number of adaptation subjects, the adaptation/test split and switch between fit and transfer. Same W-BLR configuration as the notebook; sex is not modelled as batch effect. |
| **Notebook** | [`notebooks/transfer_icbm.ipynb`](notebooks/transfer_icbm.ipynb) · [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/predictive-clinical-neuroscience/PCNtoolkit-demo-transfer/blob/main/notebooks/transfer_icbm.ipynb) |
| **PCNportal files** | [`data/pcnportal/`](data/pcnportal/): files to use in the PCNportal. It has the same 20 adaptation subjects and 65 test participants as the Collab notebook. The files include sex column so it will modelled as batch effect by PCNportal. |
| **Slides** | [`slides/`](slides/): the slides presented at the fMRI toolkit 2026. |
| **Data** | [`data/icbm_fcon1000.csv`](data/icbm_fcon1000.csv): the 85 ICBM participants, all FreeSurfer measures |

## Cite and reuse

- PCNtoolkit: see https://pcntoolkit.readthedocs.io/en/stable/getting_started/citing.html
- This material: see [CITATION.cff](CITATION.cff). Code is GPL-3.0 (as PCNtoolkit, see [LICENSE](LICENSE)); slides and text are CC BY 4.0.

Questions: [NeuroStars](https://neurostars.org/tag/pcntoolkit) · [PCNtoolkit issues](https://github.com/predictive-clinical-neuroscience/PCNtoolkit/issues)
