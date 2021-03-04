## Linting

The process of running linters is mostly automated. Molecule is configured to lint so you will see linting errors when you run `molecule test` (if your code has any). There is also a pre-commit hook that lints your code and performs other validations before allowing a `git commit` or `npm run commit` command to go through. If you followed the [Setting Up Development Environment](#setting-up-development-environment) section, you should be all set to have your code automatically linted before pushing changes to the repository.

**Please note that before creating a pull request, all lint errors should be resolved.** If you would like to view all the linting tools we are using then check out `.husky/pre-commit`.

### Fixing ansible-lint Errors

You can manually run ansible-lint by executing the following command in the project's root:

```shell
pip3 install -r requirements.txt
ansible-lint
```

Most errors will be self-explanatory and simple to fix. Other errors might require testing and research. Below are some tips on fixing the trickier errors.

#### [208] File permissions unset or incorrect

Do research to figure out the minimum permissions necessary for the file. After you change the permission, test the role because changing file permissions often results in causing errors.

#### [301] Command should not change things if nothing needs doing

This error can be solved by telling Ansible what files the command creates or deletes. When you specify what file a `command:` or `shell:` creates/deletes, Ansible will check for the presence or absence of the file to determine if the system is already in the desired state. If it is in the desired state, then Ansible skips the task. Refer to the [documentation for ansible.builtin.command](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/command_module.html) for further details.

Here is an example of code that will remove the error:

```yaml
- name: Run command if /path/to/database does not exist (with 'args' keyword)
  command: /usr/bin/make_database.sh db_user db_name
  args:
    creates: /path/to/database # If the command deletes something, then you can swap out creates with removes
```

#### [305] Use shell only when shell functionality is required

We should only be using Ansible's shell task when absolutely necessary. If you get this error then test if replacing `shell:` with `command:` resolves the error. If that does not work, then you can add a comment at the end of the line that says `# noqa 305`.
