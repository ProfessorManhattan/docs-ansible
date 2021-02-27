## Example Playbook

With the dependencies installed, all you have to do is add the role to your main playbook. The role handles the `become` behavior, so you can simply add the role to your playbook without worry:

```lang-yml
- hosts: all
  roles:
    - {{ role_name }}
```
