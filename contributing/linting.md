## Linting

The process of running linters is mostly automated. Molecule is configured to lint so you will see linting errors when you run `molecule test` (if your code has any). There are a few gaps that are filled in by [pre-commit](https://pre-commit.com/). If you followed the [Setting Up Development Environment](), you should have noticed that one of the lines you need to execute to set up the project is:

```shell
pre-commit install
```

After installing pre-commit, your code will be automatically be sent through several different linting and formatting engines whenever you run `git commit`. **In general, you should fix all linting errors instead of adding rules to ignore the lint error.** In the following sections, we will give tips on resolving specific lint errors.

### ansible-lint

You can manually run ansible-lint by executing the following command in the project's root:

```shell
pip3 install -r requirements
ansible-lint
```

Most errors will be self-explanatory and simple to fix. Other errors might require testing and research. Below are some tips on fixing the trickier errors.

#### [208] File permissions unset or incorrect

Do some research to figure out the minimum permissions necessary for the file. After you change the permission, test the role because changing file permissions often results in causing errors.

#### [301] Command should not change things if nothing needs doing

This error can be solved by telling Ansible what files the command creates or deletes. When you specify what file a `command:` or `shell:` creates/deletes, Ansible will check for the presence/absence of the file to determine if the system is already in the desired state. If it is in the desired state, then Ansible skips the task. Refer to the [documentation for ansible.builtin.command](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/command_module.html) for further details.

Here is a quick example that will remove the error:

```yaml
- name: Run command if /path/to/database does not exist (with 'args' keyword)
  command: /usr/bin/make_database.sh db_user db_name
  args:
    creates: /path/to/database # If the command deletes something, then you can swap out creates with removes
```

#### [305] Use shell only when shell functionality is required

We should only be using Ansible's shell task when absolutely necessary. If you get this error then test if replacing `shell:` with `command:` resolves the error. If that does not work, then you can add a comment at the end of the line that says `# noqa 305`.