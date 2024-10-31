# Ansible Collection - `artemisbeta.ubuntu_setup`
![Static Badge](https://img.shields.io/badge/test-molecule-blue)
![Static Badge](https://img.shields.io/badge/ansible-2.17-black)
![Static Badge](https://img.shields.io/badge/ubuntu-22.04%20%7C%2023.04-purple)

Personal set of Ansible roles for deployments and installations on Ubuntu.

|||
|-------|------|
|Install Pyenv|[![artemisbeta.ubuntu_setup.pyenv](https://github.com/artemis-beta/ansible-ubuntu-setup/actions/workflows/test_pyenv.yaml/badge.svg)](https://github.com/artemis-beta/ansible-ubuntu-setup/actions/workflows/test_pyenv.yaml)|
|Install LazyVim|[![artemisbeta.ubuntu_setup.lazyvim](https://github.com/artemis-beta/ansible-ubuntu-setup/actions/workflows/test_lazyvim.yaml/badge.svg)](https://github.com/artemis-beta/ansible-ubuntu-setup/actions/workflows/test_pyenv.yaml)|

# 🏃 Running Ansible

It is strongly recommended that a virtual environment be used to install and run Ansible, or [pyenv](https://github.com/pyenv/pyenv) be used to install a user specific Python instance.

```sh
python -m pip install requirements.txt
```

## Including the Role

Include the role within your Ansible `playbook.yaml` file:

```yaml
- name: Install Pyenv
  hosts: all
  roles:
    - artemisbeta.ubuntu_setup.pyenv
```

# 🧪 Testing with Molecule

The roles within this collection are tested using [Ansible Molecule](https://molecule.readthedocs.io/), with Ansible as the provisioner and [Podman](https://podman.io/) as the driver. To run the tests ensure all requirements are installed:

```sh
apt install -y podman
```

Launch molecule by changing to the directory of the role:

```sh
cd roles/pyenv
molecule test
```

this will spin up a Ubuntu container via Podman and execute the Molecule test stages.

## Running Individual Stages

|**Stage**|**Command**|**Description**|
|---------|-----------|---------------|
|create   | `molecule create`| Create the container instance|
|prepare  | `molecule prepare`| Run pre-test setup within the container|
|converga | `molecule converge`|Run the role|
|verify| `molecule verify` | Run post-role checks |

