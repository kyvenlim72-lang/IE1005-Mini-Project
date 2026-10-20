# IE0005: M1–M5-style notebook

Open `IE0005_M1_M5_Style.ipynb` from the project folder, beside `netflix_titles.csv`. This is a separate copy; `IE0005.ipynb` is preserved.

## Step-by-step workflow

1. Select the project's Python environment in Jupyter or VS Code. The tested analysis package versions are recorded in `m1_m5_project_outputs/analysis_requirements.txt`. Install those packages if needed.
2. Restart the kernel and run the notebook from the first cell. Read the code-origin table: course adaptations and additions beyond the supplied M1–M5 examples are labelled.
3. Inspect the raw genre (`listed_in`), description and rating columns. Review missing values, exclusions and repeated descriptions before using the cleaned dataset.
4. Review the binary target inherited from the original notebook. R, TV-MA and NC-17 are grouped as “18+”; other accepted ratings are “Not 18+”. These names are project proxies, not an official shared age threshold.
5. Review the training-set plots and statistics. Explain which genres and description patterns appear related to the target.
6. Compare the majority baseline, M4-style decision tree and three Naive Bayes input choices. The notebook selects the Naive Bayes input using training cross-validation, then reports results on the reserved test set.
7. Inspect the confusion matrix, per-rating results and misclassified descriptions. Explain why accuracy alone is insufficient.
8. Use the optional M5 clustering and anomaly sections to discuss unusual description formats. They do not automatically remove records or determine age ratings.
9. Run the demonstration in section 14. Edit the example genres and descriptions, then discuss the predictions and their limitations.
10. Present the accompanying slides. Add team names and contributions, verify your explanations against the notebook, and rehearse the demonstration.

## Verified run

- Source: 8,807 titles; cleaned: 8,686.
- Training: 6,948; test: 1,738.
- Selected model: Naive Bayes using description and genre.
- Test accuracy: 70.8%; macro F1: 0.707.
- Majority baseline accuracy: 53.9%.

The notebook exports the cleaned data, exclusions, split assignments, metrics, predictions and figures into `m1_m5_project_outputs`. Rerunning it refreshes these outputs. The PowerPoint is a snapshot of the verified run; update it if the experiment changes.

## Course style and additions

M1/M2 supply the read–inspect–clean–plot workflow; M4 supplies the split–fit–predict–evaluate pattern; M5 supplies optional clustering and anomaly exploration. No M3 notebook was supplied.

Text vectorization, Naive Bayes, pipeline cross-validation, additional evaluation metrics and reproducibility/export helpers are marked as extensions E1–E5. Most modelling extensions already existed in the original notebook. The notebook includes references for these APIs rather than claiming they came from the course examples.

Repeated exact descriptions retain their first record, following the original approach. Conflicting labels among duplicates are a limitation. A single split and short synopses do not establish reliable ratings for new titles; the demonstration is a project model, not a content-rating service.

The cleaning cell is preserved verbatim from `IE0005.ipynb`; the following adapter changes column names and prepares derived features and audit exports without further filtering or normalizing the data.
