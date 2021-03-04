## Setting Up Development Environment

Before contributing to this project, you will have to make sure you have the tools that are utilized. The following is required for developing and testing this Ansible project:

### Requirements

* **Ansible** >=2.10
* **Python 3**, along with the `python3-netaddr` and `python3-pip` libraries (i.e. `sudo apt-get install python3 python3-netaddr python3-pip`)
* Docker - This is optional but required for running the Docker Molecule tests
* **Node.js** >=12
* **VirtualBox** - Used for running the molecule tests

### Getting Started

With all the requirements installed, navigate to the root directory and run the following commands to install the Python dependencies and Ansible Galaxy dependencies:

```terminal
npm i
```

This will install all the dependencies and automatically register a pre-commit hook. More specifically, `npm i` will:

1. Install the Node.js dependencies
2. Install a pre-commit hook using [husky](https://www.npmjs.com/package/husky)
3. Install the Python requirements
4. Install the Ansible Galaxy requirements

### NPM Tasks Available

With the dependencies installed, you can see a list of the available commands by running `npm run info`. This will log a help menu to the console informing you about the available commands and what they do. After running the command, you will see something that looks like this:

```
```

For example, `npm run build` will run the `build` step described above. You can see exactly what each command is doing by checking out the `package.json` file.

### Troubleshooting Python Issues

If you are experiencing issues with the Python modules, you can make use of `venv` by running the following before running the above commands:

```terminal
python3 -m venv venv
source venv/bin/activate
```
