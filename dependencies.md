## Dependencies

 At the beginning of the play, the galaxy dependencies listed in `meta/main.yml` will run. These dependencies are configured to only run once per playbook. If you include more than one of our roles in your playbook that have dependencies in common then the dependency installation will be skipped after the first run. Some of our roles also utilize helper roles which help keep our [main playbook]() DRY. A full list of the dependencies is below:

 {{ role_dependencies }}

If you are handling the installation of these dependencies with another role, you can bypass the installation of the **galaxy dependencies** by setting the `install_role_dependencies` variable to `false`. The helper dependencies are still required.

Most of our roles rely on Ansible Galaxy collections. Before you run this role, you will need to install the dependencies and the collections by running:

```
ansible-galaxy install -r requirements.yml
```
