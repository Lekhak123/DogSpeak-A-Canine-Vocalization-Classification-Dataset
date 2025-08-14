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

Please check the [huggingface repo](https://huggingface.co/datasets/ArlingtonCL2/DogSpeak_Dataset) to download the dataset.

### Dataset Summary

**DogSpeak** is a large-scale, "in-the-wild" canine vocalization dataset designed to advance research in animal communication and computational bioacoustics. Unlike previous datasets recorded in controlled environments, DogSpeak is sourced from tens of thousands of online social media videos, capturing a wide array of natural, organic interactions. This dataset is designed to challenge and foster the development of more robust bioacoustic models capable of handling the inherent noise and variability of real-world recordings.

The dataset contains `77,202` bark sequences (referred to as "Barkseqs") from `156` individual dogs across `5` breeds: Chihuahua, German Shepherd, Husky, Pitbull, and Shiba Inu.

**File Structure:**
The dataset is organized into a simple directory structure for easy access:

```

/DogSpeak/
├── dogspeak_released/
│   ├── dog_1/
│   │   ├── 0_chihuahua_M_dog_1.wav
│   │   └── ...
│   ├── dog_2/
│   │   ├── 1_chihuahua_M_dog_2.wav
│   │   └── ...
│   └── dog_7a/
│   │   ├── 0_chihuahua_M_dog_7a.wav
│   │   └── ...
│   └── dog_7b/
│   │   ├── 5957_chihuahua_M_dog_7b.wav
│   │   └── ...
└── metadata.csv

````

Each dog's audio clips are located in a folder named with a sequential `dog_id` (e.g., `dog_1`, `dog_2`). All audio files are in `.wav` format.

**Note on File Structure:** Due to a repository limit of 10,000 files per directory, the original `dog_7` folder, which contained over 11,000 files, has been split into two subdirectories: `dog_7a` and `dog_7b`. These directories contain the same audio files as the original `dog_7` folder but are divided to comply with the upload limits.

**Metadata:**
The `metadata.csv` file provides key information for each audio clip, formatted as follows:

| Column | Description |
|---|---|
| `filename` | The new, unique filename for the audio clip. |
| `breed` | The breed of the dog. |
| `sex` | The biological sex of the dog (`male` or `female`). |
| `dog_id` | The unique ID of the dog. |


### Citation

If you use this dataset in your research, please cite the following paper. This is a crucial requirement for proper academic attribution.

```bibtex
@inproceedings{lekhak2025dogspeak,
    author = {Lekhak, Hridayesh and Wang, Theron S. and Dang, Tuan M. and Zhu, Kenny Q.},
    title = {DogSpeak: A Canine Vocalization Classification Dataset},
    year = {2025},
    publisher = {ACM},
    booktitle = {Proceedings of the 33rd ACM International Conference on Multimedia},
    series = {MM '25},
    address = {Dublin, Ireland},
    doi = {10.1145/3746027.3758298}
}
````

### License

The DogSpeak dataset is licensed under the **Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License**. This means that you are free to share and adapt the material for non-commercial purposes, provided you give appropriate credit and distribute any new works under the same license.

```
