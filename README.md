# CryoPROS: addressing preferred orientation in single-particle cryo-EM through AI-generated auxiliary particles
CryoPROS is a computational framework specifically designed to tackle misalignment errors caused by preferred orientation issues in single-particle cryo-EM. It addresses these challenges by co-refining synthesized and experimental data. By utilizing a self-supervised deep generative model, CryoPROS synthesizes auxiliary particles that effectively eliminate these misalignment errors through a co-refinement process.

## Video Tutorial
[TBD]

## Preprint
For more details, please refer to the preprint ["Addressing preferred orientation in single-particle cryo-EM through AI-generated auxiliary particles"](https://www.biorxiv.org/content/10.1101/2023.09.26.559492v1).

## The List of Available Demo Cases

| dataset |expected result link |
| ----------- | ----------------- |
| HA-trimer (EMPIAR-10096) | [TBD] |

# Installation

CryoPROS is free software developed in Python and is available as a Python package. You can access its distributions [on GitHub](https://github.com/mxhulab/crypros).

## Prerequisites

- Python version 3.10.
- NVIDIA CUDA library 10.2 or later installed in the user's environment.

## Dependencies

[TBD]

## Preparation of CUDA Environment

### Creating and Activating a Conda Virtual Environment

First, create a Conda virtual environment named `CRYOPROS_ENV` with Python 3.10 by running the following command:
```
conda create -n CRYOPROS_ENV python==3.10
```

After creating the environment, activate it using:
```
conda activate CRYOPROS_ENV
```

### Installing PyTorch and Torchvision

Install the versions of PyTorch and torchvision that correspond to your specific environment, particularly matching your CUDA Driver Version. Use the following command, replacing `{x.x.x}` with the appropriate version numbers and `{xxx}` with your CUDA version:

```
pip install torch=={x.x.x} torchvision=={x.x.x} --extra-index-url https://download.pytorch.org/whl/cu{xxx}
```

For example, to install PyTorch 1.11.0 and torchvision 0.12.0 for CUDA Driver 10.2, you would use:
```
pip install torch==1.11.0+cu102 torchvision==0.12.0+cu102 --extra-index-url https://download.pytorch.org/whl/cu102
```

## Installing CryoPROS
```
pip install cryoPROS-1.3-cp310-cp310-linux_x86_64.whl
```

## Verifying Installation
You can verify whether cryoPROS has been installed successfully by running the following command:
```
cryopros-generate -h
```
This should display the help information for cryoPROS, indicating a successful installation.

# Tutorial

## Workflow Diagram of CryoPROS

![workflow](images/workflow.jpg)

CryoPROS is composed of two primary modules: the generative module and the co-refinement module, and includes an optional sub-module for heterogeneous reconstruction.

## Five Executable Binaries Included in CryoPROS

CryoPROS consists of five executable binaries, as listed in the following table:

| binary name | category | purpose | options/argument |
| ------------ |--------- | --------- | --------------- |
| `cryopros-train ` | core |Training the deep generative neural network that generates auxiliary particles. | |
| `cryopros-generate` | core | Generating auxiliary particles. | |
| `cryopros-uniform-pose` | utility | | [see](#optionsarguments-of-cryopros-uniform-pose) |
| `cryopros-gen-mask` | utility | | |
| `cryopros--recondismic` | optional | | |

## Integrating CryoPROS's Executable Binaries with Cryo-EM Softwares to Address Preferred Orientation Challenges

Using cryoPROS to address the preferred orientation issue in single-particle cryo-EM involves integrating these submodules with other cryo-EM software, such as Relion, CryoSPARC, EMReady and cryoDRGN. This integration is user-defined and can be customized based on different datasets. To demonstrate the effectiveness of cryoPROS, case studies are provided.

## Case Study: Achieving 3.49Å Resolution for an Untitled HA-Trimer (EMPIAR-10096)

# Options/Arguments

<a name="cryopros-train"></a>
## Options/Arguments of `cryopros-train`

[TBD]

<a name="cryopros-generate"></a>
## Options/Arguments of `cryopros-generate`

[TBD]

<a name="cryopros-uniform-pose"></a>
## Options/Arguments of `cryopros-uniform-pose`

[TBD]

<a name="cryopros-gen-mask"></a>
## Options/Arguments of `cryopros-gen-mask`

[TBD]

<a name="cryopros-recondismic"></a>
## Options/Arguments of `cryopros-recondismic`

[TBD]
