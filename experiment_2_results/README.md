Stimuli and behavioral results for **experiment 2 (CIFAR-10)** in

#### Tal Golan, Prashant C. Raju & Nikolaus Kriegeskorte (2020) PNAS 
## Controversial stimuli: Pitting neural networks against each other as models of human cognition

[(Project home)](https://github.com/kriegeskorte-lab/PNAS_2020_Controversial_Stimuli)

### Human behavioral responses CSV - column definitions
|column name| description |
| -- | -- |
|subject code | *Exp2x_Syy* where *x* is replication (a or b) and *yy* is subject number. No subject participated in both replications. |
|image | stimulus filename (without extension). These images are found in `stimuli_presented_in_behavioral_experiment`. |
|image_repetition | *0* if this is the first trial with this stimulus for the current subject, *1* if it is a repeated presentation.|
|response_category | Which of the ten categories this line describes. Note that for each trial, ten response categories were collected.|
|targeted_model_1 | for controversial stimuli, the identity of the first targeted model.<sup>1</sup> |
|targeted_model_2 | for controversial stimuli, the identity of the second targeted model.<sup>1</sup> |
|targeted_class_1 | for controversial stimuli, the identity of the first target class.<sup>1</sup> |
|targeted_class_2 | for controversial stimuli, the identity of the second target class.<sup>1</sup> |
|category_rating | category presence probability assigned by the subject for the particular image and response category. Possible values: *0*, *0.25*, *0.5*, *0.75* or *1*. This is the main outcome variable of the experiment. |
| first_reaction_rt | time in milliseconds until first GUI interaction.<sup>2</sup>|
| rt | time millisecond until trial completion.<sup>2</sup>|
| trial | trial number (chronological). First trials were demo trials and are excluded from the data files.|

<sup>1</sup>: The controversial stimuli were optimized such that *targeted_model_1* detects *targeted_class_1* but not *targeted_class_2*, and *targeted_model_2* detects *targeted_class_2* but not *targeted_class_1*. These four columns are left empty for natural CIFAR examples.

<sup>2</sup>: The reaction times are trial-specific, not response-category specific.

---

### Model naming
| model handle in filenames and csvs | model name in the paper (see SI Table 2) |
| -- | -- |
| finetuned_vgg16_bn | finetuned VGG-16 |
| JEM-dscrmntv | Wide-Resnet |
| Wen_PCN_A6 | Wen PCN-A6 |
| robustness_resnet50_linf_8| Engstrom ℓ<sub>∞</sub>|
| robustness_resnet50_l2_1.0 | Engstrom ℓ<sub>2</sub>|
| Gaussian_KDE | Gaussian KDE |
| JEM-20 | Grathwohl JEM-20 |

---

### Image filename naming convention
Controversial stimuli: `(targeted_model_1)_(target_class_1)_vs_(targeted_model_2)_(target_class_2).png`

Natural examples: `CIFAR_10_test_(index in experiment)_(original CIFAR10 test index)_(image class).png`
