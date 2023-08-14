## Installation

- Follow the Isaac Sim [documentation](https://docs.omniverse.nvidia.com/isaacsim/latest/install_workstation.html) to install the latest Isaac Sim release (2022.2.1). 

- Add to `.bashrc`
```
export ISAACSIM_PATH="${HOME}/.local/share/ov/pkg/isaac_sim-2022.2.1"
export ISAACSIM_PYTHON_EXE="${ISAACSIM_PATH}/python.sh"
```

- Clone this repository

```
cd OmniIsaacGymEnvs
ln -s ${ISAACSIM_PATH} _isaac_sim
./orbit.sh --conda isaacsim
conda activate isaacsim
pip install -e .
```

- The following error may appear during the initial installation. This error is harmless and can be ignored.

```
ERROR: pip's dependency resolver does not currently take into account all the packages that are installed. This behaviour is the source of the following dependency conflicts.
```

- Test installation

```
python -c "import torch; print('torch version:', torch.__version__); print('CUDA is available:', torch.cuda.is_available()); import omni; print('Omniverse imported')"

python scripts/random_policy.py
```