## Setting Up Development Environment

Before contributing to this project, you will have to make sure you have the tools that are utilized. The following is required for developing and testing this Ansible role:

### Requirements

* **Ansible** >=2.10
* **Python 3**, along with the `python3-netaddr` and `python3-pip` libraries (i.e. `sudo apt-get install python3 python3-netaddr python3-pip`)
* **Docker** - Used for running the Docker tests (this is not fully working, see [this issue]({{ repository.playbooks }}/-/issues/183))
* **VirtualBox** - Used for running the molecule tests

### Dependencies

With all the requirements installed, navigate to the root directory and run the following commands to install the Python dependencies and Ansible Galaxy dependencies:

```terminal
pip3 install -r requirements.txt
ansible-galaxy install -r requirements.yml
pre-commit install
git submodule update --init --recursive
```

If you are experiencing issues with the Python modules, you can make use of `venv` by running the following before running the above commands:

```terminal
python3 -m venv venv
source venv/bin/activate
```