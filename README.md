The repository contains script examples completed during the work in the Centre for Bioelectric Interfaces of HSE University as Researcher. 

The scripts are mainly related to the work on the [Real-time encephalography Project](https://bioelectric.hse.ru/en/real_time_encephalography). You can read more about the study and its results in the article - [Short-delay neurofeedback facilitates training of the parietal alpha rhythm
](https://iopscience.iop.org/article/10.1088/1741-2552/abc8d7/meta?casa_token=1bC6CorvnqgAAAAA:vfcz9YIFVDAMUn-nZlbko1jsE4dao-l8EuzewnpLGn1s82AqRSmNVjpg1kbL9vEaIwQEKkL65SE-6UM).


The main idea is often encountered unreliable results of NFB intervention could be associated with large feedback latency values.

We engaged our subjects into a parietal alpha power unpregulating paradigm facilitated by visual NFB based on the individually extracted envelope of the alpha-rhythm at P4 electrode. NFB was displayed either as soon as an electroencephalographic (EEG) envelope was processed, or with an extra 250 or 500ms delay. The feedback training consisted of 15 two-minute long blocks interleaved with 15 s pauses. We have also recorded 2min long baselines immediately before and after the training.

As a result, feedback latency was shown to be a critical parameter in a range of applications that imply learning. 


The project contains many experiments. This repository only provides examples of technical scripts to show how to work with encephalographic data recorded during neurofeedback training.

**Stack:** `Python`

**IDE:** `Jupyter Notebook`


| № |Description | Packages&Libraries|
| ------------------------ | ----------- | ---------- | 
| [01 - Check real latency](https://github.com/belinskayaA/low-latency-nfb/blob/eaddb0e7da43b7b66edbfbe029088bc47aa67042/Check_real_latency.ipynb) | Since we were studying the effect of neurofeedback delay, it was important for us to always check what the REAL delay was in our experiment. Since we are giving real-time feedback, we need time to record the signal, extract the target rhythm envelope, and visualize the feedback. Real-time envelope extraction requires the use of specific signal analysis techniques, which also produce a delay, since we cannot accurately predict how the signal will change in the future. To find out how long this whole process takes, we can take an offline record and calculate the instantaneous alpha amplitude on it, extracted from an EEG with zero delay in an offline analysis. After correlating these two signals, this way we will know the accuracy of our neurofeedback and its delay. | `pylab` `numpy` `scipy.signal` `scipy.stats` `h5py` |
| [02 - Alpha frequency changing  ](https://github.com/belinskayaA/low-latency-nfb/blob/46ed9d73b14003a4b9e13918535b92cda95645ed/Alpha_frequency_changing.ipynb) | The therapeutic effects of neurofeedback (NFB) remain controversial. Therefore, it is very important to check that your experimental condition (with real feedback) differs from the control condition (where the subject sees a signal that has nothing to do with his neuronal events). This script shows how you can quickly check on two recordings that the alpha rhythm of the subjects changed under different experimental conditions. | `pylab` `numpy` `scipy.signal` `scipy.stats` `pandas` `seaborn` `glob` `os` `sys`|
| [03 - Detection of alpha bursts for learning curves](https://github.com/belinskayaA/low-latency-nfb/blob/ed58e02dbb71ec1af5b893e75d83da724e2861a2/Detection_of_alpha_bursts_for_learning_curves.ipynb) | EEG rhythmic activity is non-stationary and consists of a succession of transient burst events. Changes in mean magnitude of alpha activity may be caused by variations in burst duration, burst amplitude, and the incidence rate of such bursts. Accordingly, alpha spindles can be considered as discrete structural units whose characteristics could change as the result of NFB training. This script shows how we calculated all these metrics. | `matplotlib.pyplot` `numpy` `scipy.signal` `scipy.stats` `pandas` `seaborn` `h5py` `os`|
| [04 - Comparison of feedback groups](https://github.com/belinskayaA/low-latency-nfb/blob/ed58e02dbb71ec1af5b893e75d83da724e2861a2/Comparison_of_feedback_groups.ipynb) | We were interested in how subjects could feel to distinguish feedback with different latencies. Therefore, in this study we explored the effects of feedback latency using a within-subjects paradigm. The order of conditions is an important factor for within-subject design through the influence of previous sessions. To compensate for the order effect we used the balanced design and assigned to each subject a unique sequence of conditions which resulted in 4!= 24 participants in our study. This script shows how we can compare different metrics in an in-group design (ANOVA, t-test, linear regression).| `statsmodels.api` `numpy` `statsmodels.formula.api` `pandas` `seaborn` `numpy` `pylab`|
