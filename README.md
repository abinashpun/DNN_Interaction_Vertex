# VertexML

A machine learning approach to find the interaction vertices of the reconstructed tracks at SpinQuest experiment.


## Data
Monte Carlo simulated Raw data for SpinQUestt was used for the analysis. Raw data contains `~200k` Drell-Yan events with $\mu^{+/-}$ particles' information. The structure of the input data is;
```
X = [charge, station1[x, y, z], station1[x, y, z], station3[px, py, pz], station3[px, py, pz]]
y = [vertex[x, y, z, px, py, pz]]
```

## Neural Network Architecture

```
* * * * * *     * * * * * * * * * * * * * * *     * * * * * * * * * * * * * * *     * * * * * *
* Input   *     * Classification Layer      *     * Regression layer          *     *         *
* Tensor  * --> * 2 Linear hidden layers    * --> * 3 Linear hidden layers    * --> * Target  *
*         *     * ReLu activation function  *     * ReLu activation function  *     * Tensor  *
* * * * * *     * CrossEntropyLoss          *     * MSELoss                   *     * * * * * *
                * Adam optimizer            *     * Adam optimizer            *
                * * * * * * * * * * * * * * *     * * * * * * * * * * * * * * *
```

### Testing This Module

It is highly recommended to use the [`conda`](https://github.com/conda-forge/miniforge) environment to test this module.
```bash
conda env create -f environment.yml
conda activate vertexml
```
