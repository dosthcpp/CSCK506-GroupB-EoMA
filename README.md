# CSCK506 Deep Learning — Group B · EoMA Project

**Task:** Train a CNN to distinguish healthy lungs (NORMAL) from pneumonia-infected lungs (PNEUMONIA) on the Kaggle *Chest X-Ray Images (Pneumonia)* dataset, and present the work in a group report (2,000–2,500 words).
**Submission due:** 23 November 2026

## Repository layout
- `notebooks/` — one notebook per experiment, named `<owner>_<topic>` (agreed convention; commit **with outputs** at each milestone)
- `data/` — split definitions and data notes only. **Images are not stored here** — download the dataset from Kaggle.
- `results/` — metrics as small CSV files
- `report/` — report draft sections

## Dataset (verified counts, clean copy)
| Split | NORMAL | PNEUMONIA |
|---|---|---|
| train | 1,341 | 3,875 |
| test | 234 | 390 |
| val (original) | 8 | 8 |

The original validation set is only 16 images, so we carve our own validation split from the training data (see below) and keep the original test set untouched for the final evaluation.

## Shared split — `data/shared_split_seed42.csv`
Stratified 85:15 split of the 5,216 training images (seed 42):
- `train_shared`: 4,433 images (NORMAL 1,140 / PNEUMONIA 3,293)
- `val_shared`: 783 images (NORMAL 201 / PNEUMONIA 582)

⚠️ **Caveat:** this is an *image-level* split — 367 patient IDs appear in both partitions. Whether to regenerate a patient-wise split is a team decision.

## Milestones
- **9 Nov** — roles agreed, dataset downloaded, EDA posted
- **13 Nov** — baseline CNN
- **16 Nov** — iteration (augmentation / overfitting strategies)
- **20 Nov** — model frozen, test-set evaluation
- **22 Nov** — report draft
- **23 Nov** — submission

## Roles
- Data & EDA — Doyeon Baek (@dosthcpp)
- Baseline CNN, architecture & hyperparameter tuning — Mark McLeod
- Evaluation & analysis — volunteered (TBC in minutes)
- Report lead — **open**
- Minutes — Mark McLeod
