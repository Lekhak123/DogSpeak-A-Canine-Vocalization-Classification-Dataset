---
license: cc-by-nc-sa-4.0
tags:
- Canine Vocalization
- Dog Bark Analysis
- Animal Communication
- Vocalization Dataset
- Machine Learning
- Computational Bioacoustics
- Bioacoustics Classification
pretty_name: 'DogSpeak: A Canine Vocalization Classification Dataset'
size_categories:
- 10K<n<100K
---

# DogSpeak: A Canine Vocalization Classification Dataset

**Paper:** https://dl.acm.org/doi/10.1145/3746027.3758298

**Dataset:** https://huggingface.co/datasets/ArlingtonCL2/DogSpeak_Dataset

## Dataset Summary

**DogSpeak** is a large-scale canine vocalization dataset designed to advance research in animal communication and computational bioacoustics.

Unlike previous canine vocalization datasets recorded in controlled environments, DogSpeak is sourced from a large collection of online videos and captures a diverse range of naturally occurring dog vocalizations recorded in real-world conditions.

The dataset contains **77,202 Bark Sequences (Barkseqs)** from **156 individual dogs** across **5 breeds**:

* Chihuahua
* German Shepherd
* Husky
* Pitbull
* Shiba Inu

In addition to breed labels, DogSpeak provides the biological sex of the dog (`male` or `female`) associated with each vocalization.

## Related Dataset

Researchers may also find our longitudinal canine vocalization dataset useful.

**Canine Age Transition Vocalization Dataset (CATVD):**

https://huggingface.co/datasets/ArlingtonCL2/Canine-Age-Transition-Vocalization-Dataset

CATVD contains **79,142 Bark Units (BUs)** extracted from **55,718 Bark Sequences (Barkseqs)** totaling approximately **11.4 hours** of vocalizations from **125 individual dogs** across **6 breeds**.

The dataset includes:

* Age in months
* Developmental age group labels
* Breed metadata
* Bark type annotations
* Elemental Dog Bark Unit (EDBU) transcripts
* Temporal Bark Unit alignments

and is specifically designed for longitudinal studies of canine vocal development.

### Important Note Regarding Dataset Overlap

Some individual dogs may appear in both the DogSpeak dataset and the Canine Age Transition Vocalization Dataset.

If you use both datasets for training, evaluation, or benchmarking, we strongly recommend checking for overlapping dogs and avoiding train/test leakage. In many cases, it may be preferable to use only one of the datasets for a given experiment.

## File Structure

```text
DogSpeak/
├── dogspeak_released/
│   ├── dog_1/
│   │   ├── 0_chihuahua_M_dog_1.wav
│   │   └── ...
│   ├── dog_2/
│   │   ├── 1_chihuahua_M_dog_2.wav
│   │   └── ...
│   ├── dog_7a/
│   │   ├── 0_chihuahua_M_dog_7a.wav
│   │   └── ...
│   └── dog_7b/
│       ├── 5957_chihuahua_M_dog_7b.wav
│       └── ...
└── metadata.csv
```

Each dog's audio clips are located in a folder named with a sequential `dog_id` (for example `dog_1`, `dog_2`, etc.).

All audio files are stored in WAV format.

### Note on File Structure

Due to repository limits on the number of files per directory, the original `dog_7` directory was divided into `dog_7a` and `dog_7b`.

These folders contain the same data as the original directory and exist solely to satisfy repository file-count constraints.

## Metadata

The `metadata.csv` file provides the following information for each Barkseq:

| Column   | Description                         |
| -------- | ----------------------------------- |
| filename | Unique Barkseq filename             |
| breed    | Dog breed                           |
| sex      | Biological sex (`male` or `female`) |
| dog_id   | Unique dog identifier               |

## Loading the Dataset

```python
from pathlib import Path
import pandas as pd
import soundfile as sf

root = Path("DogSpeak")

meta = pd.read_csv(root / "metadata.csv")

row = meta.iloc[0]

audio, sr = sf.read(
    root / "dogspeak_released" / row["filename"]
)

print(audio.shape)
print(sr)
```

## Recommended Usage

DogSpeak is most useful for:

* Breed classification
* Sex classification
* Canine vocalization modeling
* Audio representation learning
* Bioacoustic foundation model pretraining
* Large-scale canine acoustic analysis

Researchers interested in age-dependent vocal development should additionally consider the Canine Age Transition Vocalization Dataset.

## Citation

If you use this dataset in your research, please cite:

```bibtex
@inproceedings{lekhak2025dogspeak,
  title={DogSpeak: A Canine Vocalization Classification Dataset},
  author={Lekhak, Hridayesh and Wang, Theron S and Dang, Tuan M and Zhu, Kenny Q},
  booktitle={Proceedings of the 33rd ACM International Conference on Multimedia},
  pages={13369--13375},
  year={2025}
}
```

## License

The DogSpeak dataset is licensed under the **Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0)**.

You may share and adapt the dataset for non-commercial purposes, provided that appropriate credit is given and derivative works are distributed under the same license.
