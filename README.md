# PCNtoolkit demo: transfer a pretrained normative model

Material from the PCNtoolkit hands-on at the [Donders (f)MRI Toolkit](https://www.ru.nl/en/donders-institute/agenda/donders-fmri-toolkit), 20 November 2026.

You have scans from one site and want a Z-score for every person: how far is their brain measure from what is normal for their age and sex? You can **fit your own normative model** on your healthy controls, or **transfer** a model the PCN lab already trained on 67,000 people from 89 sites. This repo compares both on real data.

**Example used throughout:** the ICBM site of the open FCON1000 dataset (85 healthy adults, ages 19–85), cortical thickness of the left precentral gyrus, and the pretrained model `BLRw_ct_DES_lifespan_67K_89sites`.

| | |
|---|---|
| **Web app** | [Borrow or build?](https://predictive-clinical-neuroscience.github.io/PCNtoolkit-demo-transfer/): change the number of controls (5–60) and the `random_state` of the split, switch between your own model and transfer |
| **Notebook** | [`notebooks/transfer_icbm.ipynb`](notebooks/transfer_icbm.ipynb) · [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/predictive-clinical-neuroscience/PCNtoolkit-demo-transfer/blob/main/notebooks/transfer_icbm.ipynb) |
| **Slides** | [`slides/`](slides/) (PDF, including the PCNportal walkthrough) |
| **Data** | [`data/icbm_fcon1000.csv`](data/icbm_fcon1000.csv): the 85 ICBM participants, all FreeSurfer measures |
| **PCNportal files** | [`data/pcnportal/`](data/pcnportal/): the same 20 controls (adaptation) and 65 test participants, in PCNportal's template format |

## What you will see

With 20 healthy controls, picked with `NormData.train_test_split(splits=(0.24, 0.76), random_state=0)` as on the slides, scored on the 65 people neither model has seen:

| | outside \|Z\| > 2 (should be ~5%) | MACE (0 = perfect) |
|---|---|---|
| fit on my site only | 15.4% | 0.097 |
| transfer the 67K model | 7.7% | 0.097 |

Without transfer, 37% of these healthy people would have \|Z\| > 2: ICBM measures this region thinner than the sites in the 67K model.

The bigger difference is the age curve. Fitted on 20 people, your own model is almost flat across age; the transferred model keeps the decline with age it learned from 67,000 people. With very few controls (5) transfer breaks, because it estimates each sex's spread from 2–3 people; from about 30 controls the scores of both models converge. The web app shows all of this, averaged over 8 splits (8 values of `random_state`).

## Run the notebook

- **Colab:** click the badge above. The first cell installs `pcntoolkit==1.4.0`; restart the session if Colab asks.
- **Locally:** `pip install pcntoolkit==1.4.0` (or `conda`, see the [PCNtoolkit docs](https://pcntoolkit.readthedocs.io/en/latest/)), then open the notebook in Jupyter.

The notebook downloads the 67K model (~4 MB) from the lab's [SURFdrive share](https://surfdrive.surf.nl/s/Mb6mZyFmJeCaPcZ?dir=/zip) and loads FCON1000 with `load_fcon1000()`. Change `N_CONTROLS`, `SEED` or `REGION` to explore.

## Use PCNportal instead (no code)

1. Go to [pcnportal.dccn.nl](https://pcnportal.dccn.nl/) › *Compute here!* and choose a cortical thickness (Destrieux) model.
2. Upload `data/pcnportal/icbm_test.csv` as test data and `data/pcnportal/icbm_adaptation.csv` as adaptation data.
3. Results arrive by email. Note that the portal's models may differ from the 67K model used here, so numbers can differ slightly.

## Cite and reuse

- PCNtoolkit: see [CITATION.cff](https://github.com/predictive-clinical-neuroscience/PCNtoolkit/blob/main/CITATION.cff) in the PCNtoolkit repo.
- Pretrained lifespan models: the approach is described in Rutherford et al. (2022), *eLife*, [doi:10.7554/eLife.72904](https://doi.org/10.7554/eLife.72904); cite the reference given with the specific model you use.
- PCNportal: Barkema et al. (2023), *Wellcome Open Research*, [doi:10.12688/wellcomeopenres.19591.2](https://doi.org/10.12688/wellcomeopenres.19591.2).
- Data: [FCON1000](https://fcon_1000.projects.nitrc.org/fcpClassic/FcpTable.html), ICBM site (A.C. Evans), released openly by the 1000 Functional Connectomes Project; derived FreeSurfer measures as distributed with PCNtoolkit.
- This material: see [CITATION.cff](CITATION.cff). Code is GPL-3.0 (as PCNtoolkit, see [LICENSE](LICENSE)); slides and text are CC BY 4.0.

Questions: [NeuroStars, tag pcntoolkit](https://neurostars.org/tag/pcntoolkit) · [PCNtoolkit issues](https://github.com/predictive-clinical-neuroscience/PCNtoolkit/issues)

## Maintainers: GitHub Pages

The web app is `docs/index.html`, a single self-contained file. In the repo's *Settings › Pages*, choose *Deploy from a branch*, branch `main`, folder `/docs`. It is then served at `https://<owner>.github.io/PCNtoolkit-demo-transfer/`.
