# Emotion Classification in DreamBank Dream Reports

Code for the paper "Compatibility, Not Confirmation: What Emotion Patterns
in 27,952 DreamBank Reports Can and Cannot Tell Us About Dream Theories."

## What this does
Classifies the dominant Hall and Van de Castle (HVDC) emotion code in
dream reports, using TF-IDF features and a linear SVM. The model is
evaluated with five-fold cross-validation grouped by dreamer, and
compared with two baseline classifiers (most-frequent and stratified).

## Data
Reports come from DreamBank (https://dreams.ucsc.edu). The data file is
not included in this repository. Download the data from the source,
save it as `train.csv` in the same folder as the notebook, and check
DreamBank's terms of use.

Expected columns: id, name, number, time, date, gender, age, report,
character, emotion (27,952 rows).

## How to run
1. Install the packages: `pip install -r requirements.txt`
2. Put `train.csv` in the same folder as the notebook.
3. Open `dream_emotion_classification.ipynb` and run all cells from the top.

The first run downloads the NLTK English stopword list. The saved
outputs in the notebook come from a full run.

## Main results
Five-fold cross-validation grouped by dreamer, on the 11,808 reports
with an emotion code (72 dreamers or series):

| Model | Macro F1 |
|---|---|
| Linear SVM | 0.640 ± 0.018 |
| Most-frequent baseline | 0.103 |
| Stratified baseline | 0.196 |

Random seed: 42. Exact scores can differ slightly across scikit-learn
versions because of how folds are assigned.

## Limitations
Only the first-listed emotion code per report is used. The data come
from 72 dreamers, and the largest series is 17% of coded reports.

## Citation
If you use this code, please cite the archived version:
[Sahar Tebyanian]. (2026). Code for dreamer-grouped emotion classification of
DreamBank dream reports (v1.0.0) [Software]. Zenodo. Tebyanian, S. (2026). Code for dreamer-grouped emotion classification of DreamBank dream reports (v1.0.0) [Software]. Zenodo. https://doi.org/10.5281/zenodo.23542304

## Licence
MIT. See the LICENSE file.
