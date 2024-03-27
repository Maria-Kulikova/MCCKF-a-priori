# Condensed MCC-KF and IMCC-KF implementation methods
This repository contains MATLAB functions with various implementation methods of discrete-time Maximum Correntropy Criterion Kalman Filter (MCC-KF) by Izanloo et.al. (2016)[^1] and improved MCC-KF (IMCC-KF) by Kulikova (2017)[^2] with a scalar adjusting parameter. They are given in a priori form (the predicted form), i.e., the first measurement is available at the initial step and, hence, the measurement update stage comes first. All such methods can be written in the so-called condensed form, i.e., without division on the time and measurement updates. Thus, only condensed algorithms are mentioned in this repository. Two-stage implementations can be easily obtained from algorithms <a href="https://github.com/Maria-Kulikova/MCCKF-a-posteriori">here</a>.

## References
Each code (implementation method) includes the exact reference where the particular algorithm was published. 
If you use these codes in your research, please, cite the corresponding articles mentioned in the codes or in the list below.  

## Remark
The codes have been presented here for their instructional value only. They have been tested with care but are not guaranteed to be free of error and, hence, they should not be relied on as the sole basis to solve problems. 

# Steps to reproduce
- `Test_MCCKFs` is the script that performs Monte Carlo runs for solving filtering problem by various MCC-KF implementations.
- `Test_IMCCKFs` is the script that performs Monte Carlo runs for solving filtering problem by various IMCC-KF implementations.
- `Test_PI` is the script for calculating the Performance Index (Baram Proximity Measure) by various filtering algorithms. 
- `Illustrate_XP` is the script that illustrates the obtained estimates and the diagonal entries of the error covariance matrix (over time). You can find its call at the end of the script above, which is commented. Just delete this comment sign.
- `Illustrate_PI` is the script that illustrates the Performance Index (Baram Proximity Measure) calculated by various filtering algorithms. 
- `Simulate_Measurements` stands for simulating the state-space model and generating the measurements for the filtering methods.

When the state is estimated, the resulted errors of the MCC-KF implementation methods should be the same because they are mathematically equivalent to each other. Their numerical properties differ, but the ill-conditioned test examples are not given here. Similarly, the resulted errors of the IMCC-KF implementation methods should be the same because they are mathematically equivalent to each other. 

# List of the MCC-KF implementation methods 
**Riccati recursion-based KF implementation methods:**
| Function | Description |
| ---: | :--- |
| `Riccati_MCCKF_standard` |  the Conventional implementation in one-step condensed form by Kulikova (2019)[^3]|

# List of the IMCC-KF implementation methods
**Riccati recursion-based KF implementation methods:**
- Conventional algorithms:
  -  `Riccati_IMCCKF_standard` is the condensed form by Kulikova (2019), <a href="http://doi.org/10.1109/ICSTCC.2019.8885950">DOI</a>, <a href="https://arxiv.org/abs/2310.18750">ArXiv</a>
- Square-root algorithms by using Cholesky factorization:
  -  `Riccati_IMCCKF_SRCF_QL`   is the Square-Root Covariance Filter (SRCF) with lower triangular factors by Kulikova (2019), <a href="http://doi.org/10.1109/ICSTCC.2019.8885950">DOI</a>, <a href="https://arxiv.org/abs/2310.18750">ArXiv</a>
  -  `Riccati_IMCCKF_eSRCF_QL`  is the Extended SRCF with lower triangular factors by Kulikova (2019), <a href="http://doi.org/10.1109/ICSTCC.2019.8885950">DOI</a>, <a href="https://arxiv.org/abs/2310.18750">ArXiv</a>
   
### Chandrasekhar recursion-based KF implementation methods:
- Conventional algorithms:
  - `Chandrasekhar_IMCCKF1` is the Conventional implementation by Kulikova (2020), <a href="https://doi.org/10.1109/TAC.2019.2919341">DOI</a>, <a  href="https://arxiv.org/abs/2311.01165">ArXiv</a>
  - `Chandrasekhar_IMCCKF2` is the Conventional implementation by Kulikova (2020), <a href="https://doi.org/10.1109/TAC.2019.2919341">DOI</a>, <a  href="https://arxiv.org/abs/2311.01165">ArXiv</a>
  - `Chandrasekhar_IMCCKF3` is the Conventional implementation by Kulikova (2020), <a href="https://doi.org/10.1109/TAC.2019.2919341">DOI</a>, <a  href="https://arxiv.org/abs/2311.01165">ArXiv</a>
  - `Chandrasekhar_IMCCKF4` is the Conventional implementation by Kulikova (2020), <a href="https://doi.org/10.1109/TAC.2019.2919341">DOI</a>, <a  href="https://arxiv.org/abs/2311.01165">ArXiv</a>

[^1]: Izanloo, R. and Fakoorian, S.A. and Yazdi, H.S. and Simon D. (2016) Kalman filtering based on the maximum correntropy criterion in the presence of non-Gaussian noise, in: 2016 Annual Conference on Information Science and Systems (CISS), 2016, pp. 500-505. <a href="https://doi.org/10.1109/CISS.2016.7460553">DOI</a>
[^2]: Kulikova M.V. (2017) Square-root algorithms for maximum correntropy estimation of linear discrete-time systems in presence of non-Gaussian noise. Systems and Control Letters, 108: 8-15. <a href="https://doi.org/10.1016/j.sysconle.2017.07.016">DOI</a>, <a href="https://arxiv.org/abs/1611.03686">PDF on ArXiv</a>
[^3]: Kulikova, M.V. (2019) One-Step Condensed Forms for Square-Root Maximum Correntropy Criterion Kalman Filtering, Proceedings of the 23rd International Conference on System Theory, Control and Computing (ICSTCC),  Sinaia, Romania, pp. 13-18. <a href="http://doi.org/10.1109/ICSTCC.2019.8885950">DOI</a>, <a href="https://arxiv.org/abs/2310.18750">PDF on ArXiv</a>
