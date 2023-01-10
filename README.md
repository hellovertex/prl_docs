# prl_docs

The project consists of the packages

- [prl_environment](https://github.com/hellovertex/prl_environment)
- [prl_baselines](https://github.com/hellovertex/prl_baselines)
- [prl_reinforce](https://github.com/hellovertex/prl_reinforce)
- [prl_api](https://github.com/hellovertex/prl_api)
- [prl_frontend](https://github.com/hellovertex/prl_frontend)

----

## Installation -- Ubuntu 20.04

1. Create python virtualenv

```commandline
python3 -m venv <NAME_OF_VENV>
```

2. Activate the new python virtualenv and update pip

```commandline
   source <PATH_TO_VENV>/bin/activate
&& pip install -U pip
```

3. Install necessary `prl`-namespace packages from sources:

#### The **Poker Environment package** `prl-environment` including submodules

```commandline
   git clone --recurse-submodules https://github.com/hellovertex/prl_environment.git
&& cd prl_environment
&& git submodule update --recursive --remote
&& pip install requests
&& pip install .  # use pip install -e . optionally for development
```

#### The Reinforcement Learning **baseline agents package** `prl-baselines`

```commandline
   git clone --recurse-submodules https://github.com/hellovertex/prl_baselines.git
&& cd prl_baselines
&& git submodule update --recursive --remote
&& pip install .

# install the c++ hand evaluator library
pip install "pybind11[global]"`
cmake prl/baselines/cpp_hand_evaluator/cpp
make
# in case cmake fails:
sudo apt-get update && sudo apt-get install build-essential
# in case make fails:
in case make fails: `sudo apt install libpython3.10-dev` 
```

#### The **Reinforcement Learning package** `prl-reinforce` (does not work without the previous too intsalled)

```commandline
   git clone https://github.com/hellovertex/prl_reinforce.git
&& cd prl_reinforce
&& pip install .
```


Note: If you did not clone using `--recurse-submodules`,
run `git submodule update --recursive --remote` with `--init` 

Note: You can use `pip install -e .` during development to make the package editable.

## Usage

----
### Training
#### Set environment variables
- export `PRL_BASELINE_MODEL_PATH`=<PATH_TO_"baseline_model_ckpt.pt"_FILE>
- export `ALGO_CKPT_DIR`=<PATH_TO_RLLIB_CHECKPOINT_DIR>

### Development
