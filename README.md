# prl_docs

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

- The **Poker Environment package** `prl-environment` including submodules

```commandline
   git clone --recurse-submodules https://github.com/hellovertex/prl_environment.git
&& cd prl_environment
&& git submodule update --recursive --remote
&& pip install requests
&& pip install .  # use pip install -e . optionally for development
```

- The Reinforcement Learning **baseline agents package** `prl-baselines`

```commandline
   git clone --recurse-submodules https://github.com/hellovertex/prl_baselines.git
&& cd prl_baselines
&& git submodule update --recursive --remote
&& pip install .
```

- The **Reinforcement Learning package** `prl-reinforce` (does not work without the previous too intsalled)

```commandline
   git clone https://github.com/hellovertex/prl_reinforce.git
&& cd prl_reinforce
&& pip install .
```


Note: If you did not clone using `--recurse-submodules`,
run `git submodule update --recursive --remote --init` instead

Note: You can use `pip install -e .` during development to make the package editable.

## Usage

----


## Development
Using Pycharm, add an SSH interpreter to develop, deploy, and debug directly on A Cloud VM.
I used AWS EC2-instances. 
Install repos there, copy host-ip and .pem file path to ssh-intrepreter-wizard and finally set
sync directory locations. Done. You can now run the debugger on the remote machine.
